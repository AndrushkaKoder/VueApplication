<script setup>

defineProps({
	title: String,
	price: Number,
	image: String,
	isLiked: Boolean,
	inCart: Boolean,
	clickInCart: Function,
	clickFavorite: Function
})

</script>

<template>
	<div
			class="relative flex flex-col w-full border border-slate-100 rounded-3xl p-8 cursor-pointer shadow-sm transition hover:shadow-xl hover:transform hover:-translate-y-2"
	>
		<div @click="clickFavorite" class="absolute top-8 left-8">
			<img :src="isLiked ? '/icons/like-2.svg' : '/icons/like-1.svg'" alt="Favorite"/>
		</div>
		<div>
			<img :src="image" class="w-full" alt="Sneaker"/>
			<p class="mb-16">{{ title }}</p>
		</div>
		<div class="flex justify-between">
			<div class="flex flex-col items-center">
				<span class="text-slate-200">Цена:</span>
				<span class="font-bold">{{ price }} руб.</span>
			</div>
			<img @click="clickInCart" :src="inCart ? '/icons/checked.svg' : '/icons/plus.svg'" alt="Plus"/>
		</div>
	</div>
</template>

<style scoped lang="scss">

</style>