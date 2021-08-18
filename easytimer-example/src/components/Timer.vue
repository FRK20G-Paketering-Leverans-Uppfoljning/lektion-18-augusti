<template>
  <div class="hello">
    <button @click="start">Starta timer</button>
    <button @click="stop">Stoppa timer</button>
    <p>{{ currentTime }}</p>
  </div>
</template>

<script>
import Timer from 'easytimer.js';

export default {
  name: 'Timer',
  props: {
    msg: String
  },
  data() {
    return {
      timer: new Timer(),
      currentTime: ''
    }
  },
  methods: {
    start() {
      this.timer.start();
      this.timer.addEventListener('secondsUpdated', () => {
        this.currentTime = this.timer.getTimeValues().toString();
      });
    },
    stop() {
      this.timer.stop();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
