<template>
 <nav class="menu">
   <ul>
     <li v-for="(item, index) in menuItems" :key="index" @mouseover="hoverStart" @mouseleave="hoverEnd">
       {{ item.name }}
     </li>
   </ul>
 </nav>
</template>

<script>
import * as THREE from 'three';
import { gsap } from 'gsap';

export default {
  data() {
    return {
      menuItems: [
        { name: 'Home', path: '/' },
        { name: 'About', path: '/about' },
        { name: 'Services', path: '/services' },
        { name: 'Contact', path: '/contact' },
        // 他のメニュー項目を追加
      ],
    };
  },
  methods: {
    hoverStart(event) {
      gsap.to(event.target, { scale: 1.2, duration: 0.3 });
    },
    hoverEnd(event) {
      gsap.to(event.target, { scale: 1, duration: 0.3 });
    },
  },
};
</script>

<style lang="scss">
// ここにSCSSスタイルを書く
</style>