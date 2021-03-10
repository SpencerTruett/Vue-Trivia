<template>
  <div>
    <h1 class="title">STAR WARS TRIVIA</h1>
    <div class="questions">
      <div v-for="card in trivia" :key="card.id">
        <FlashCard :card="card" />
      </div>
    </div>
  </div>
</template>

<script>
import trivia from "../trivia";
import FlashCard from "./FlashCard";

export default {
  components: { FlashCard },
  data() {
    return {
      trivia: [...trivia]
    };
  }
};
</script>

<style>
.title {
  color: goldenrod;
  text-align: center;
  font-size: 80px;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
}
.questions {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
.flat-button {
  background: transparent;
  border: none;
  cursor: pointer;
  margin-bottom: 10px;
  font-size: 20px;
  color: goldenrod;
}
</style>