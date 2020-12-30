<script context="module" lang="ts">
	export function preload() {
		return this.fetch(`blog.json`)
			.then((r: { json: () => any }) => r.json())
			.then((posts: { slug: string; title: string; html: any }[]) => {
				return { posts };
			});
	}
</script>

<script lang="ts">
	export let posts: { slug: string; title: string; html: any }[];
</script>

<svelte:head>
	<title>Blog</title>
</svelte:head>

<div class="w-full">
	<h1 class="text-center text-3xl">Recent posts</h1>

	<ul class="my-4">
		{#each posts as post}
			<!-- we're using the non-standard `rel=prefetch` attribute to
					tell Sapper to load the data for the page as soon as
					the user hovers over the link or taps it, instead of
					waiting for the 'click' event -->
			<li>
				<a
					class="text-xl"
					rel="prefetch"
					href="blog/{post.slug}">{post.title}</a>
			</li>
		{/each}
	</ul>
</div>
