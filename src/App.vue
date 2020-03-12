<template>
  <div id="app">
    <div class="board-container">
      <div v-for="(tile, index) in board.flat()" :key="index" class="board-tile"> {{tile}} </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      board: [
        [null, null, null, null],
        [null, null, null, null],
        [null, null, null, null],
        [null, 2, 2, null]
      ]
    };
  }
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.board-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr;
  grid-column-gap: 10px;
  grid-row-gap: 15px;
  height: 500px;
  width: 500px;
  border: 5px solid rgba(255, 210, 126, 0.89);
}

.board-tile {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid black;
  font-size: 36px;
  font-weight: bold;
}
</style>
