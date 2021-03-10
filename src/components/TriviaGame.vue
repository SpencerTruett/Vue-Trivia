<template>
  <div>
    <div v-for="card in trivia" :key="card.id">
      <FlashCard :card="card" />
    </div>
  </div>
</template>

<script>
import { trivia } from "../trivia";
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
</style>