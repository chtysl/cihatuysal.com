<script context="module">
	const allPosts = import.meta.glob('./*.{md,svx}');

	let body = [];
	for (let path in allPosts) {
		body.push(
			allPosts[path]().then(({ metadata }) => {
				return { path, metadata };
			})
		);
	}
	export const load = async () => {
		const posts = await Promise.all(body);

		return {
			props: {
				posts
			}
		};
	};
</script>

<script>
	// @ts-nocheck

	export let posts;

	const dateSortedPosts = posts.slice().sort((post1, post2) => {
		return new Date(post2.metadata.date) - new Date(post1.metadata.date);
	});
</script>

<div class="flex justify-center items-center ">
	<ul class="">
		{#each dateSortedPosts as { path, metadata: { title, date } }}
			<li>
				<a
					class="hover:text-blue-500 text-3xl"
					href={path.replace('./', '/blog/').replace('.md', '').replace('.svx', '')}>{title}</a
				>
				<p class="">{new Date(date).toDateString()}</p>
			</li>
		{/each}
	</ul>
</div>
