<template>
	<div class="container-xl">
		<div class="row">
			<div class="col-12">
				<Carousel />
			</div>
		</div>
	</div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import Carousel from '~/components/carousel.vue'

@Component({
	components: { Carousel }
})
export default class IndexPage extends Vue {
}
</script>

<style lang="scss" scoped>

</style>
