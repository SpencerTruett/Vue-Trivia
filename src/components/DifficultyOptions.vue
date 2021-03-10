<template>
  <div>
    <button>Easy</button>
    <button>Medium</button>
    <button>Hard</button>
    <button>Show All</button>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
button {
  border: 5px solid black;
  color: white;
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
  background-color: goldenrod;
  color: black;
}
</style>