<template>
	<section class="columns">
		<div class="container column is-half">
			<h1 class="title">Trailer</h1>
			<iframe :src="url" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
			</iframe>
		</div>
	</section>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Trailer extends Vue {
	@Prop() public url!: string;
}
</script>

<style scoped>
div iframe {
	width: 560px;
	height: 315px;
}
</style>
