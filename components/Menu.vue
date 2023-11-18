<template>
  <button @click.prevent="showMenu">Menu</button>
  <nav class="menu" v-if="menuVisible">
    <ul>
      <li v-for="(item, index) in menuItems" :key="index" @mouseover="hoverStart" @mouseleave="hoverEnd">
        <a :href="item.path">{{ item.name }}</a>
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
      menuVisible: false,
    };
  },
  methods: {
    showMenu() {
      this.menuVisible = !this.menuVisible;
      this.$nextTick(() => {
        if (this.menuVisible) {
          gsap.from(this.$el, { opacity: 0, y: '-100%', duration: 0.5 });
        } else {
          gsap.to(this.$el, { opacity: 0, y: '-100%', duration: 0.5 });
        }
      });
    },
  },
};
</script>

<style lang="scss">
.menu {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  padding: 0;
  margin: 0;
  height: 300px; /* 円の直径 */
  width: 300px; /* 円の直径 */
  position: relative;
}
.menu ul {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  padding: 0;
  margin: 0;
  height: 300px; /* 円の直径 */
  width: 300px; /* 円の直径 */
  position: relative;
}

.menu li {
  position: absolute;
  width: 100px; /* メニュー項目の幅 */
  height: 100px; /* メニュー項目の高さ */
  text-align: center;
  line-height: 100px; /* メニュー項目の高さと同じにする */
}

.menu li:nth-child(1) {
  top: 50%;
  left: 0;
  transform: translate(-50%, -50%);
}

.menu li:nth-child(2) {
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
}

.menu li:nth-child(3) {
  top: 50%;
  left: 100%;
  transform: translate(-50%, -50%);
}

.menu li:nth-child(4) {
  top: 100%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>