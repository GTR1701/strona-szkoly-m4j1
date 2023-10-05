<script lang="ts">
	import '../styles.css';
</script>

<body class="app">

	<section>
		<slot />
	</section>

</body>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		width: 100%;
	}

	section {
		flex: 1;
		display: flex;
		flex-direction: column;
		width: 100%;
		box-sizing: border-box;
	}
</style>
