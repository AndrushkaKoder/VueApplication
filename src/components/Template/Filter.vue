<script setup>
defineProps({
	onChangeSelect: Function,
	onSearchQuery: Function
})
</script>

<template>
	<form method="get" action="" class="flex justify-between items-center gap-5" data-form="filter">
		<div class="filter_area">
			<select @change="onChangeSelect" name="filter" class="py-2 px-3 border-gray-400 rounded outline-none bg-white">
				<option selected>Сортировать</option>
				<option value="-price">Дорогие</option>
				<option value="price">Бюджетные</option>
			</select>
		</div>
		<div class="search_area">
			<input @input="onSearchQuery" type="search" name="title" placeholder="Найди идеальные сникеры"
			       class="border-b p-3 pb-2 outline-none"
			>
			<!--			<button type="submit"-->
			<!--			        class="border bg-blue-500 p-4 px-6 rounded-md">-->
			<!--				<svg width="30" height="15" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">-->
			<!--					<path-->
			<!--							d="M15.25 15.25L11.8855 11.8795L15.25 15.25ZM13.75 7.375C13.75 9.06576 13.0784 10.6873 11.8828 11.8828C10.6873 13.0784 9.06576 13.75 7.375 13.75C5.68424 13.75 4.06274 13.0784 2.86719 11.8828C1.67165 10.6873 1 9.06576 1 7.375C1 5.68424 1.67165 4.06274 2.86719 2.86719C4.06274 1.67165 5.68424 1 7.375 1C9.06576 1 10.6873 1.67165 11.8828 2.86719C13.0784 4.06274 13.75 5.68424 13.75 7.375V7.375Z"-->
			<!--							stroke="#E4E4E4" stroke-width="2" stroke-linecap="round"/>-->
			<!--				</svg>-->
			<!--			</button>-->
		</div>
	</form>
</template>

<style scoped>

</style>