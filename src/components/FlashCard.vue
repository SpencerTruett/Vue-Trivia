<template>
  <div class="card">
    <div class="card-inner">
      <div class="question">
        <h4>{{ card.question }}</h4>
        <button>Answer</button>
      </div>
      <div class="answer">
        <h4>{{ card.answer }}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"]
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
  font-size: 16px;
  cursor: pointer;
}

.card {
  background-color: transparent;
  width: 300px;
  height: 200px;
  border: 1px solid goldenrod;
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
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 60px;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
}
.answer {
  background-color: goldenrod;
  color: black;
  transform: rotateY(180deg);
}
</style>