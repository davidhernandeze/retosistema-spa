<template>
  <div class="home">
    <div class="screen-container">
      <arcade-button></arcade-button>
      <screen></screen>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Screen from '@/components/Screen.vue'
import ArcadeButton from '../components/ArcadeButton'
export default {
  name: 'home',
  components: {
    ArcadeButton,
    Screen
  }
}
</script>

<style lang="scss">
.home {
  display: grid;
  justify-items: center;
}
</style>
