<script>
	import { goto } from '$app/navigation';
</script>

<div class="navbar bg-base-100">
	<div class="flex-1">
		<a on:click={() => goto('/')} class="btn btn-ghost normal-case text-xl">Cihat Uysal</a>
	</div>
	/* <div class="flex-none">
		<button class="btn btn-square btn-ghost">
			<a on:click={() => goto('/blog')}>Blog</a>
		</button>
	</div> */
</div>
