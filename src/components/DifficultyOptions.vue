<template>
  <div>
    <button :class="{ active: difficulty === 'easy' }" @click="selectDifficulty('easy')">Easy</button>
    <button :class="{ active: difficulty === 'medium' }" @click="selectDifficulty('medium')">Medium</button>
    <button :class="{ active: difficulty === 'hard' }" @click="selectDifficulty('hard')">Hard</button>
    <button :class="{ active: difficulty === 'all' }" @click="selectDifficulty('all')">Show All</button>
  </div>
</template>

<script>
export default {
  props: ["difficulty"],
  methods: {
    selectDifficulty(difficulty) {
      this.$emit("difficultyHasChanged", difficulty);
    }
  }
};
</script>

<style scoped>
button {
  background-color: transparent;
  text-shadow: -1px 0 #1d91f2, 0 1px #1d91f2, 1px 0 #1d91f2, 0 -1px #1d91f2;
  color: black;
  padding: 15px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  cursor: pointer;
  margin: 0 2px;
  font-weight: bold;
}
button.active {
  background-color: transparent;
  text-shadow: -1px 0 red, 0 1px red, 1px 0 red, 0 -1px red;
  color: black;
}
</style>