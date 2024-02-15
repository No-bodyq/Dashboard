<script>
	import '../app.pcss';
	import Sidebar from './sidebar.svelte';
	import Navbar from './navbar.svelte';

	let expanded = false;
</script>

<svelte:head>
	<title>Dashboard</title>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;500;600;700;800&amp;display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<body>
	<side>
		<Sidebar {expanded}></Sidebar>
	</side>

	<main>
		<Navbar />
		<slot />
	</main>
</body>

<style>
	* {
		margin: 0px;
		padding: 0px;
		font-family: 'Open Sans', sans-serif;
	}
	body {
		display: grid;
		grid-template-columns: 1fr 20fr;
		height: 100vh;
        width: 100vi;
	}
	side {
		box-shadow: 1px 1px 6px 0px gray;
		height: 100vh;
	}

	main {
		margin-left: 20px;
	}
</style>
