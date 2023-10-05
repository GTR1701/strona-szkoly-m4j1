<script lang="ts">
	import Header from './Header.svelte';
	import './styles.css';
</script>

<body class="app">
	<Header />

	<main>
		<figure style="background-image: url('https://images.unsplash.com/photo-1504639725590-34d0984388bd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1974&q=80');		">
			<figcaption><h1>Zespół Szkół Elektroniczno-Telekomunikacyjnych w Lesznie</h1></figcaption>
		</figure>
		<slot />
	</main>

	<footer>
		<h2>ZSET w Lesznie</h2>
	</footer>
</body>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		width: 100%;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		width: 100%;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}

	figure {
		width: 100%;
		background-size: cover;
		background-position: 0 -50rem;
		background-repeat: no-repeat;
		height: fit-content;
		margin: 2rem 0;
	}

	figcaption {
		margin: 10rem;
		color: white;
		text-align: center;
		background-color: rgba(0, 0, 0, 0.6);
		padding: 1rem;
	}
</style>
