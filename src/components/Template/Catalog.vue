<script setup>
import {onMounted, reactive, ref, watch} from "vue";
import axios from "axios";
import Product from "@/components/Product.vue";
import Filter from "@/components/Template/Filter.vue";

const products = ref([]);

const filter = reactive({
	sortValue: '',
	searchValue: {
		inputValue: '',
		inputName: ''
	}
})

const onChangeSelect = (event) => {
	filter.sortValue = event.target.value
}

const onChangeSearch = (event) => {
	event.preventDefault();
	filter.searchValue.inputName = event.target.name
	filter.searchValue.inputValue = `*${event.target.value}*`;
}

async function fetchProducts() {
	let productsApiPath = 'https://5acc35653482aef3.mokky.dev/products'
	try {

		let queryParams = {
			sortBy: filter.sortValue,
		}

		if (filter.searchValue.inputValue) {
			let key = filter.searchValue.inputName;
			queryParams[key] = filter.searchValue.inputValue
		}

		products.value = await axios.get(productsApiPath, {params: queryParams})
				.then(result => result.data);
	} catch (error) {
		console.error(error.message)
	}
}

// hook
onMounted(() => {
	fetchProducts();
});

// watches
watch(() => filter.sortValue, () => {
	fetchProducts('sortBy', filter.sortValue);
})

watch(() => filter.searchValue.inputValue, () => {
	fetchProducts(filter.searchValue.inputName, filter.searchValue.inputValue)
})

const inCart = () => {
	alert('In cart!');
};

// check available
async function productsAvailable() {
	return Object.keys(products.value).length > 0;
}
</script>

<template>
	<section class="catalog">

		<div class="catalog_content" v-if="productsAvailable()">
			<div class="section_title flex xl:flex-row sm:flex-col sm:gap-5 justify-between">
				<h2 class="text-4xl md:text-center sm:text-center">Все кроссовки</h2>
				<Filter
						:on-change-select="onChangeSelect"
						:on-search-query="onChangeSearch"
				/>
			</div>
			<div class="catalog_items grid xl:grid-cols-4 md:grid-cols-2 sm:grid-cols-1 gap-3 my-8">
				<Product
						v-for="product in products"
						:key="product.id"
						:id="Number(product.id)"
						:title="product.title"
						:price="Number(product.price)"
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