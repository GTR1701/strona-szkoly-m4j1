<script lang="ts">
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';

	let scale: number[] = [1, 1, 1];
	let color: string[] = [];
	let classNames: string[] = [
		'informatyk',
		'programista',
		'teleinformatyk'
	];

	const kierunki = [
    {
        "id": "1",
        "kierunek": "Technik Informatyk",
		'route': "/informatyk",
		"bgImage": 'https://images.unsplash.com/photo-1562408590-e32931084e23?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80'
    },
    {
        "id": "2",
        "kierunek": "Technik Programista",
		'route': "/programista",
		'bgImage': 'https://images.unsplash.com/photo-1516259762381-22954d7d3ad2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2089&q=80'
    },
    {
        "id": "3",
        "kierunek": "Technik Teleinformatyk",
		'route': "/teleinformatyk",
		'bgImage': 'https://images.unsplash.com/photo-1544197150-b99a580bb7a8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80'
    }
]
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Strona szkoły" />
</svelte:head>


<h1>Witaj na stronie ZSET</h1>
<h1>Kierunki dostępne w naszej szkole</h1>

<section>
	{#each kierunki as { id, kierunek, bgImage, route }, i}
		<a
			href={route}
			id={id}
			style="margin: 1rem 0; text-decoration: none; color: {color[i]}; transition: 0.5s; background-image: url({bgImage}); background-size: cover; background-position: center; background-repeat: no-repeat; scale: {scale[i]}"
			on:focus={(e) => {
				color[i] = 'white';
			}}
			on:mouseover={(e) => {
				color[i] = 'white';
				scale[i] = 1.1;
			}}
			on:mouseleave={(e) => {
				color[i] = '';
				scale[i] = 1;
			}}
			class={classNames[i]}
			>
				<h1>{kierunek}</h1>
			</a>
	{/each}
</section>

<article>
	<h1 class="article-header">Aktualności</h1>
	<p class="article-paragraph">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sint possimus eius eos accusamus perspiciatis, soluta debitis porro earum neque unde. Impedit explicabo fugiat consequatur illo et assumenda debitis vitae consequuntur! Lorem ipsum dolor sit, amet consectetur adipisicing elit. At reprehenderit quos quidem excepturi. Impedit numquam, enim ducimus maxime ipsam ad adipisci quos magni temporibus explicabo tenetur fuga, delectus illo incidunt.</p>
</article>

<style>
	article {
		width: 80%;
		margin: 5rem auto;
	}

	.article-header {
		font-size: 2rem;
		width: fit-content;
		margin: 0 auto;
	}

	.article-paragraph {
		font-size: 1.5rem;
		width: 80%;
		margin: 1rem auto;
		text-align: justify;
	}

	a {
		width: 80%;
		background-size: 0;
		transition: 0.5s;
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}
</style>
