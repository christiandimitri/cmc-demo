<script>
import { RouterLink, RouterView } from 'vue-router'
export default {
  data() {
    return {}
  },
  methods: {}
}
</script>

<template>
  <div class="wrapper flex flex-col justify-center">
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
    <RouterView />
  </div>
</template>

<style scoped></style>
