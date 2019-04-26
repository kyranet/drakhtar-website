<template>
	<section class="section columns">
		<div class="container column is-half" id="downloads">
			<h1 class="title">Descargas</h1>
			<div v-if="!releases.length">
				<p>No downloads available.</p>
			</div>
			<div v-else>
				<div v-for="release in releases" :key="release.id" class="tile is-parent has-text-left">
					<article class="tile is-child notification is-light">
						<p class="title">{{release.name}}</p>
						<div class="content">
							<p v-for="line in release.body" :key="release.body.indexOf(line)">{{line}}</p>
							<div class="field is-grouped">
								<p class="control">
									<a :href="release.zipball_url" class="button is-info is-outlined">
										Código
									</a>
								</p>
								<p class="control" v-for="asset in release.assets" :key="asset.id">
									<a :href="asset.browser_download_url" class="button is-dark is-outlined">
										{{asset.name}}
									</a>
								</p>
							</div>
						</div>
					</article>
				</div>
			</div>
		</div>
	</section>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Downloads extends Vue {
	@Prop() releases: Release[] = [];

	mounted() {
		this.fetchDownloads();
	}

	async fetchDownloads() {
		try {
			const results = await fetch('https://api.github.com/repos/kyranet/drakhtar/releases');
			const releases = await results.json();
			for (const release of releases) {
				release.body = release.body.split('\n');
				this.releases.push(release);
			}
		} catch {
			while (this.releases.length) this.releases.shift();
		}
	}
}

interface Release {
	url: string;
	html_url: string;
	assets_url: string;
	upload_url: string;
	tarball_url: string;
	zipball_url: string;
	id: number;
	node_id: string;
	tag_name: string;
	target_commitish: string;
	name: string;
	body: string[];
	draft: boolean;
	prerelease: boolean;
	created_at: Date;
	published_at: Date;
	author: Author;
	assets: Asset[];
}

interface Asset {
	url: string;
	browser_download_url: string;
	id: number;
	node_id: string;
	name: string;
	label: string;
	state: string;
	content_type: string;
	size: number;
	download_count: number;
	created_at: Date;
	updated_at: Date;
	uploader: Author;
}

interface Author {
	login: string;
	id: number;
	node_id: string;
	avatar_url: string;
	gravatar_id: string;
	url: string;
	html_url: string;
	followers_url: string;
	following_url: string;
	gists_url: string;
	starred_url: string;
	subscriptions_url: string;
	organizations_url: string;
	repos_url: string;
	events_url: string;
	received_events_url: string;
	type: string;
	site_admin: boolean;
}

</script>
