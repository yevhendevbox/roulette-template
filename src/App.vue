<script setup>
import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import { Roulette } from 'vue3-roulette'

import { ref } from 'vue'

const wheel = ref(null)
const items = [
  { id: 1, name: 'Banana', htmlContent: 'Banana', textColor: '#212121', background: '' },
  { id: 2, name: 'Apple', htmlContent: 'Apple', textColor: '#212121', background: '' },
  {
    id: 3,
    name: 'Orange and Purple',
    htmlContent: 'Orange<br>and Purple',
    textColor: '#212121',
    background: ''
  },
  { id: 4, name: 'Cherry', htmlContent: 'Cherry', textColor: '#212121', background: '' },
  { id: 5, name: 'Peach', htmlContent: 'Peach', textColor: '#212121', background: '' },
  { id: 6, name: 'Papaia', htmlContent: 'Papaia', textColor: '#212121', background: '' },
  { id: 7, name: 'Watermelon', htmlContent: 'Watermelon', textColor: '#212121', background: '' },
  { id: 8, name: 'Strawberry', htmlContent: 'Strawberry', textColor: '#212121', background: '' }
]

function launchWheel() {
  wheel.value.launchWheel()
}

function wheelEnded(item) {
  alert(`You won: ${item.name}`)
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <Roulette ref="wheel" :items="items" @click="launchWheel" @wheel-end="wheelEnded" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
