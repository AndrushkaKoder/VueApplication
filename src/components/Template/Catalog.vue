<script setup>
import Product from "@/components/Product.vue";

const products = {
	1: {
		title: 'Мужские Кроссовки Nike Blazer Mid Suede',
		price: 12999,
		image: '/sneakers/sneakers-1.jpg',
	},
	2: {
		title: 'Мужские Кроссовки Nike Air Max 270',
		price: 12999,
		image: '/sneakers/sneakers-2.jpg',
	},
	3: {
		title: 'Мужские Кроссовки Nike Blazer Mid Suede',
		price: 8490,
		image: '/sneakers/sneakers-3.jpg',
	},
	4: {
		title: 'Кроссовки Puma X Aka Boku Future Rider',
		price: 8990,
		image: '/sneakers/sneakers-4.jpg',
	},
	5: {
		title: 'Мужские Кроссовки Under Armour Curry 8',
		price: 15190,
		image: '/sneakers/sneakers-5.jpg',
	},
	6: {
		title: 'Мужские Кроссовки Nike Kyrie 7',
		price: 11290,
		image: '/sneakers/sneakers-6.jpg',
	},
	7: {
		title: 'Мужские Кроссовки Jordan Air Jordan 11',
		price: 10799,
		image: '/sneakers/sneakers-7.jpg',
	},
	8: {
		title: 'Мужские Кроссовки Nike LeBron XVIII',
		price: 16499,
		image: '/sneakers/sneakers-8.jpg',
	},
	9: {
		title: 'Мужские Кроссовки Nike Lebron XVIII Low',
		price: 13999,
		image: '/sneakers/sneakers-9.jpg',
	},
	10: {
		title: 'Мужские Кроссовки Nike Blazer Mid Suede',
		price: 8499,
		image: '/sneakers/sneakers-10.jpg',
	},
	11: {
		title: 'Кроссовки Puma X Aka Boku Future Rider',
		price: 8999,
		image: '/sneakers/sneakers-11.jpg',
	},
	12: {
		title: 'Мужские Кроссовки Nike Kyrie Flytrap IV',
		price: 11299,
		image: '/sneakers/sneakers-12.jpg',
	}
};

function checkProducts() {
	return Object.keys(products).length > 0;
}
</script>

<template>
	<section class="catalog">
		<h2 class="text-4xl">Все кроссовки</h2>
		<div v-if="checkProducts()" class="catalog_items grid xl:grid-cols-4 md:grid-cols-2 sm:grid-cols-1 gap-3 my-8">
			<Product v-for="product in products"
			         :title="product.title"
			         :price="product.price"
			         :image="product.image"
			         :is-liked="false"
			         :in-cart="false"
			/>
		</div>
		<div v-else class="flex justify-center my-10">
			<h2 class="font-bold text-2xl">Крутые кроссовки еще в пути, заходите позже =)</h2>
		</div>
	</section>
</template>

<style scoped>

</style>