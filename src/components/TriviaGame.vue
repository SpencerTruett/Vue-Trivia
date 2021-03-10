<template>
  <div>
    <h1 class="title">STAR WARS TRIVIA</h1>
    <button @click="hideAll" class="flat-button">HIDE ALL</button>
    <div>
      <DifficultyOptions
        :difficulty="selectedDifficulty"
        @difficultyHasChanged="handleDifficultyChange"
      />
    </div>
    <div class="questions">
      <div v-for="card in displayedTrivia" :key="card.id">
        <FlashCard :card="card" @toggle="handleToggle" />
      </div>
    </div>
  </div>
</template>

<script>
import trivia from "../trivia";
import FlashCard from "./FlashCard";
import DifficultyOptions from "./DifficultyOptions";

export default {
  components: { FlashCard, DifficultyOptions },
  data() {
    return {
      trivia: [...trivia],
      selectedDifficulty: "all"
    };
  },

  methods: {
    handleToggle(card) {
      card.answerShown = !card.answerShown;
    },
    handleDifficultyChange(difficulty) {
      this.selectedDifficulty = difficulty;
    },
    hideAll() {
      this.trivia.forEach(t => (t.answerShown = false));
    }
  },

  computed: {
    displayedTrivia() {
      if (this.selectedDifficulty === "all") {
        return this.trivia;
      }
      return this.trivia.filter(t => t.difficulty === this.selectedDifficulty);
    }
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