<script>
	import Navbar from '$lib/Navbar.svelte';
	import '../app.css';
</script>

<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/boxicons@2.1.2/css/boxicons.min.css" />
</svelte:head>
<Navbar />
<slot />
