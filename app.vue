<template>
  <div id="scene-container"></div>
</template>

<script setup>
import { onMounted } from 'vue'
import * as THREE from 'three'
import { gsap } from 'gsap'

onMounted(() => {
  // Three.jsの基本設定（シーン、カメラ、レンダラー）
  const scene = new THREE.Scene()
  const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
  const renderer = new THREE.WebGLRenderer()

  renderer.setSize(window.innerWidth, window.innerHeight)
  document.getElementById('scene-container').appendChild(renderer.domElement)

  // ドットの生成
  const geometry = new THREE.BufferGeometry().setFromPoints([
    new THREE.Vector3(-1, 0, 0),
    new THREE.Vector3(0, 1, 0),
    new THREE.Vector3(1, 0, 0),
  ])

  const material = new THREE.PointsMaterial({ color: 0xff0000, size: 0.1 })
  const points = new THREE.Points(geometry, material)

  scene.add(points)

  // GSAPによるアニメーション
  gsap.to(points.rotation, {
    duration: 2,
    x: Math.PI * 2,
    ease: 'none',
    repeat: -1
  })

  // アニメーションループ
  const animate = () => {
    requestAnimationFrame(animate)
    renderer.render(scene, camera)
  }

  animate()
})
</script>

<style>
/* CSSのスタイル設定 */
</style>
