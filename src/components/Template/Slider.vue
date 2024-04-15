<script setup>
import {Swiper, SwiperSlide} from 'swiper/vue';
import 'swiper/css/bundle';

let sliderImages = [
	'/slider/slide4.jpeg',
	'/slider/slide5.webp',
	'/slider/slide6.webp'
]
</script>

<template>
	<section class="slider">
		<swiper
				:slides-per-view="1"
				:space-between="50"
				:autoplay='true'
				:free-mode="true"
		>
			<swiper-slide
					v-for="slide of sliderImages"
			>
				<img :src="slide" alt="Slide">
			</swiper-slide>
		</swiper>
	</section>
</template>

<style scoped lang="scss">
.swiper {
	border-radius: 10px;
	height: 450px;
	max-width: 100%;
	margin: 40px auto;

	.swiper-slide {
		border-radius: 10px;

		img {
			width: 100%;
			height: 100%;
			border-radius: 10px;
			object-fit: cover;
		}
	}
}
</style>