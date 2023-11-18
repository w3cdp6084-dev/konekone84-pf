<template>
 <nav class="menu">
   <ul>
     <li v-for="(item, index) in menuItems" :key="index">
       {{ item.name }}
     </li>
   </ul>
 </nav>
</template>

<script>
export default {
 data() {
   return {
     menuItems: [
       { name: 'Home' },
       { name: 'About' },
       { name: 'Services' },
       { name: 'Contact' },
     ],
   };
 },
};
</script>

<style scoped>

</style>