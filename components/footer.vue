<template>
	<footer class="container-xl bg-dark text-white">
		<div class="row">
			<div id="footer-section-1" class="col-4">
				<h3>footer section 1</h3>
			</div>
			<div id="footer-section-2" class="col-4">
				<h3>footer section 2</h3>
			</div>
			<div id="footer-section-3" class="col-4">
				<h3>footer section 3</h3>
			</div>
		</div>
		<div class="row">
			<div class="col-md-6 text-center text-md-left">
				Logo here
			</div>
			<div class="col-md-6 text-center text-md-right">
				@{{ projectStartYear }} - {{ new Date().getFullYear() }} Localhost &reg;
			</div>
		</div>
	</footer>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'nuxt-property-decorator'

@Component
export default class Footer extends Vue {
	@Prop({ default: '' }) projectStartYear: string | undefined
}
</script>
