<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div class="router">
    <router-link to="/home">Home</router-link> |
    <router-link to="/login">Login</router-link>
  </div>
   <router-view />
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App'
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 0 24px;
  line-height: 1.5;
}
.router {
  font-size: 16px;
}
</style>
