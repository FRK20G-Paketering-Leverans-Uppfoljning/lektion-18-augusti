<template>
  <section>
    <h3>Nedräkning</h3>
    <button @click="start">Starta nedräkning</button>
    <p>{{ timeLeft }}</p>
  </section>
</template>

<script>
import Timer from 'easytimer.js';

export default {
  name: 'Countdown',
  data() {
    return {
      timer: new Timer(),
      timeLeft: ''
    }
  },
  methods: {
    start() {
      this.timer.start({ countdown: true, startValues: { seconds: 10 }});
      this.timer.addEventListener('secondsUpdated', () => {
        this.timeLeft = this.timer.getTimeValues().toString();
      });

      this.timer.addEventListener('targetAchieved', () => {
        this.timeLeft = "Time's up! Party time!!";
      });
    }
  }
}
</script>

<style>

</style>