<template>
  <div>
    <TriviaGame />
  </div>
</template>

<script>
import TriviaGame from "./components/TriviaGame";
export default {
  name: "App",
  components: {
    TriviaGame
  }
};
</script>

<style>
body {
  background-color: #6098cf;
}
</style>
