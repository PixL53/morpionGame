<template>
  <main>
    <morpionIntro v-if="step == 1" @nextStep="nextStep"></morpionIntro>
    <userRegister v-if="step == 2" @nextStep="nextStep" />
    <startGame v-if="step == 3" />
  </main>
  <iframe width="100%" height="100" scrolling="no" frameborder="no" allow="autoplay"
    src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/39910932&color=%239300a2&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true">
  </iframe>
</template>

<script>
import morpionIntro from './components/morpionIntro.vue'
import userRegister from './components/userRegister.vue'
import startGame from './components/startGame.vue'

export default {
  name: 'App',
  data() {
    return {
      step: 1
    }
  },
  methods: {
    nextStep() {
      this.step++
    }
  },
  components: {
    morpionIntro,
    userRegister,
    startGame,
  }
}
</script>

<style>
#app {
  font-family: Georgia, serif;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-color: white;
  background: url(https://images.weserv.nl/?url=i.imgur.com/6QJjYMe.jpg)
}

@import url(//fonts.googleapis.com/css?family=Vibur);

html,

body {
  background: #112 url(//images.weserv.nl/?url=i.imgur.com/6QJjYMe.jpg) center no-repeat;
  background-size: cover;
  margin: 0;
}

.logo {
  text-align: center;
  width: 65%;
  height: 140px;
  margin: auto;
  position: relative;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  user-select: none;
}

.logo b {
  font: 400 19vh "Vibur";
  color: #fee;
  text-shadow: 0 -40px 100px, 0 0 2px, 0 0 1em #ff4444, 0 0 0.5em #ff4444, 0 0 0.1em #ff4444, 0 10px 3px #000;
}

.logo b span {
  animation: blink linear infinite 2s;
}

.logo b span:nth-of-type(2) {
  animation: blink linear infinite 3s;
}

@keyframes blink {
  78% {
    color: inherit;
    text-shadow: inherit;
  }

  79% {
    color: #333;
  }

  80% {

    text-shadow: none;
  }

  81% {
    color: inherit;
    text-shadow: inherit;
  }

  82% {
    color: #333;
    text-shadow: none;
  }

  83% {
    color: inherit;
    text-shadow: inherit;
  }

  92% {
    color: #333;
    text-shadow: none;
  }

  92.5% {
    color: inherit;
    text-shadow: inherit;
  }
}
</style>