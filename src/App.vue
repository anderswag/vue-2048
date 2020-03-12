<template>
  <div id="app" @keyup='gameAction'>
    <div>Score:{{score}}</div>
    <div class="board-container">
      <div v-for="(tile, index) in board.flat()" :key="index" class="board-tile"> {{tile}} </div>
    </div>
  </div>
</template>

<script>
const KEY_CODES = {
  up: 38,
  down: 40,
  left: 37,
  right: 39
};

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
  },
  computed: {
    score() {
      return this.board.flat().reduce((a, b) => a + b, 0);
    }
  },
  mounted() {
    document.addEventListener('keyup', this.gameAction);
  },
  methods: {
    gameAction() {
      // let boardClone = JSON.parse(JSON.stringify(this.board));
      if (event.keyCode == KEY_CODES.left) {
        this.board.forEach((row, index) => {
          console.log('row', row, 'index', index);
        });
      }
    }
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
  background: #5d6c89;
  height: 500px;
  width: 500px;
  padding: 20px;
  /* border: 5px solid #f652a0; */
}

.board-tile {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fbf6f3;
  font-size: 36px;
  font-weight: bold;
}
</style>
