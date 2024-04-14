<script setup>

</script>

<template>
  <header class="flex justify-between border-b border-b-slate-300 p-8">
    <div class="logo flex items-center gap-4">
      <div class="">
        <img src="/icons/logo.png" alt="Logo" class="w-10">
      </div>
      <div class="">
        <h2 class="text-2xl font-bold">SNEAKERHEAD</h2>
        <p>Магазин шикарных кроссовок</p>
      </div>
    </div>

    <ul class="flex justify-center items-center gap-4">
      <li class="flex justify-center items-center hover:cursor-pointer">
        <img src="/icons/cart.svg" alt="Price" class="mx-3">
        <b class="text-slate-500">100500 руб.</b>
      </li>
      <li class="flex justify-center items-center">
        <img src="/icons/heart.svg" alt="Favorite" class="mx-3 hover:cursor-pointer">
        <span class="text-slate-500 hover:text-slate-300 cursor-pointer">Закладки</span>
      </li>
      <li class="flex justify-center items-center">
        <img src="/icons/cart.svg" alt="Cart" class="mx-3">
        <span class="text-slate-500 hover:text-slate-300 cursor-pointer">Корзина</span>
      </li>
    </ul>
  </header>
</template>

<style scoped>

</style>