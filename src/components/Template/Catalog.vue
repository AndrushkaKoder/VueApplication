<script setup>
import {onMounted} from "vue";
import axios, {Axios} from "axios";

import Product from "@/components/Product.vue";
import Filter from "@/components/Template/Filter.vue";

let products = null;
onMounted(() => {
	const productsApiPath = 'https://5acc35653482aef3.mokky.dev/products'
	products = axios.get(productsApiPath).then(response => response.data)
})

const props = defineProps({
	products: Array
})

const inCart = () => {
	alert('In cart!');
};

const productsAvailable = () => {
	return props.products ? props.products.length > 0 : false;
}
</script>

<template>
	<section class="catalog">

		<div class="catalog_content" v-if="productsAvailable()">
			<div class="section_title flex xl:flex-row sm:flex-col sm:gap-5 justify-between">
				<h2 class="text-4xl md:text-center sm:text-center">Все кроссовки</h2>
				<Filter/>
			</div>
			<div class="catalog_items grid xl:grid-cols-4 md:grid-cols-2 sm:grid-cols-1 gap-3 my-8">
				<Product
						v-for="product in products"
						:key="product.id"
						:title="product.title"
						:price="product.price"
						:image="product.image"
						:is-liked="false"
						:in-cart="false"
						:click-in-cart="inCart"
				/>
			</div>
		</div>

		<div v-else class="text-center">
			<h2 class="font-bold text-2xl">Крутые кроссовки еще в пути, заходите позже =)</h2>
		</div>

	</section>
</template>

<style scoped>

</style>