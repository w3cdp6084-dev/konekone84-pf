<template>
  <div>
    <Menu />
    <NuxtWelcome />
  </div>
</template>
<script>
import * as THREE from 'three';
import { gsap } from 'gsap';
import Menu from '@/components/Menu.vue'
export default {
  components: {
    Menu
  }
}
</script>
<style lang="scss">
// ここにSCSSスタイルを書く
</style>
