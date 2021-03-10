<template>
  <div class="card" :class="{ flipped: card.answerShown }">
    <div class="card-inner">
      <div class="question">
        <h4>{{ card.question }}</h4>
        <button @click="handleClick">Show Answer</button>
      </div>
      <div class="answer">
        <h4>{{ card.answer }}</h4>
        <button @click="handleClick">Show Question</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"],

  methods: {
    handleClick() {
      this.$emit("toggle", this.card);
    }
  }
};
</script>

<style>
button {
  background-color: goldenrod;
  border: none;
  color: white;
  padding: 15px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 20px;
  cursor: pointer;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
}

.card {
  background-color: transparent;
  width: 300px;
  height: 200px;
  perspective: 1000px;
  margin-top: 20px;
  font-size: 20px;
}

.card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}
.question,
.answer {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.question {
  background-color: transparent;
  color: goldenrod;
  border: 1px solid goldenrod;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 60px;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
}
.answer {
  background-color: transparent;
  color: goldenrod;
  transform: rotateY(180deg);
  border: 1px solid goldenrod;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 60px;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
}

.flipped .card-inner {
  transform: rotateY(180deg);
}
</style>