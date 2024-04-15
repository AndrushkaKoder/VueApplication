<script setup>
import DrawerHead from "@/components/Template/Drawer/DrawerHead.vue";
import CartItem from "@/components/Template/Drawer/CartItem.vue";
import DrawerFooter from "@/components/Template/Drawer/DrawerFooter.vue";
</script>

<template>
	<div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-80"></div>
	<div class="bg-white fixed top-0 right-0 h-full z-20 xl:w-1/5 md:w-3/4 sm:w-full p-3">
		<DrawerHead/>
		<div class="items scroll-auto overflow-auto h-4/5">
			<CartItem/>
			<CartItem/>
			<CartItem/>
			<CartItem/>
			<CartItem/>
			<CartItem/>
			<CartItem/>
			<CartItem/>

		</div>
		<DrawerFooter/>
	</div>
</template>

<style>

</style>