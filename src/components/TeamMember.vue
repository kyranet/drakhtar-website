<template>
	<section class="columns">
		<div class="container column is-half">
			<article class="media">
				<figure class="media-left">
					<p class="image is-128x128">
						<img class="is-rounded" :src="imageSRC" :alt="name">
					</p>
				</figure>
				<div class="media-content">
					<div class="content">
						<h3 class="subtitle">{{name}}</h3>
						<p>{{description}}</p>
					</div>
				</div>
			</article>
			<hr>
		</div>
	</section>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class TeamMember extends Vue {
	@Prop() public imageSRC!: string;
	@Prop() public name!: string;
	@Prop() public description!: string;
}
</script>

<style scoped>
figure {
	display: flex !important;
}
</style>
