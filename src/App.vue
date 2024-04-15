<script setup>
import Header from "@/components/Template/Header.vue";
import Slider from "@/components/Template/Slider.vue";
import Catalog from "@/components/Template/Catalog.vue";
import Drawer from "@/components/Template/Drawer/Drawer.vue";
</script>

<template>
  <div class="xl:w-4/5 sm:w-11/12 m-auto bg-white p-8 rounded-xl shadow-xl mt-12">
    <Header/>
    <Slider/>

    <Catalog/>
<!--	  <Drawer/>-->
  </div>
</template>

<style scoped>
</style>
