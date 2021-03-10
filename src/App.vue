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
  background-image: url("https://cdn.wallpapersafari.com/1/97/co341S.jpg");
  background-attachment: fixed;
}
</style>
