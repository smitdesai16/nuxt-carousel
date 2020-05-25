<template>
	<div class="carousel-view">
		<transition-group
			class="carousel"
			tag="div"
		>
			<div
				v-for="slide in slides"
				:key="slide.id"
				class="slide"
				:style="{ background: 'url(' + slide.image + ')' }"
			/>
		</transition-group>
		<div class="carousel-controls">
			<button class="carousel-controls__button" @click="previous">
				prev
			</button>
			<button class="carousel-controls__button" @click="next">
				next
			</button>
		</div>
	</div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class Carousel extends Vue {
	slides: any

	constructor() {
		super()

		this.slides = [
			{
				title: 'I am Slide A',
				id: 1,
				image: 'https://i.picsum.photos/id/874/300/300.jpg'
			},
			{
				title: 'I am Slide B',
				id: 2,
				image: 'https://i.picsum.photos/id/996/300/300.jpg'
			},
			{
				title: 'I am Slide C',
				id: 3,
				image: 'https://i.picsum.photos/id/651/300/300.jpg'
			},
			{
				title: 'I am Slide D',
				id: 4,
				image: 'https://i.picsum.photos/id/1080/300/300.jpg'
			},
			{
				title: 'I am Slide E',
				id: 5,
				image: 'https://i.picsum.photos/id/1049/300/300.jpg'
			}
		]
	}

	next() {
		const first = this.slides.shift()
		this.slides = this.slides.concat(first)
	}

	previous() {
		const last = this.slides.pop()
		this.slides = [last].concat(this.slides)
	}
}
</script>

<style lang="scss" scoped>
.carousel-view {
	display: flex;
	flex-direction: column;
	align-items: center;
}

.carousel {
	display: flex;
	justify-content: center;
	align-items: center;
	overflow: hidden;
	width: 100%;
}

.slide {
	flex: 0 0 20em;
	height: 20em;
	margin: 1em;
	display: flex;
	justify-content: center;
	align-items: center;
	border: 0.1em dashed #000;
	border-radius: 50%;
	transition: transform 0.3s ease-in-out;
}

.slide:first-of-type {
	opacity: 0;
}

.slide:last-of-type {
	opacity: 0;
}
</style>
