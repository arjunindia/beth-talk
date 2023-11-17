<script>
	import { Code, Slide, Step } from '@components'
	import bun from '../images/bun.svg'
	import elysia from '../images/elysia.svg'
	import turso from '../images/turso.svg'
	import htmx from '../images/htmx.png'
	import saltyAom from '../images/saltyAom.jpg'
	import elysiaSpeed from '../images/elysia_speed.jpg'
	import featureSheet from '../images/feature-sheet.webp'
	import AuthorCard from '../components/AuthorCard.svelte'
	const animateCard = () => {
		document.querySelectorAll('.card').forEach((card) => {
			card.classList.add('animate-fade-up')
		})
	}
	const resetCard = () => {
		document.querySelectorAll('.card').forEach((card) => {
			card.classList.remove('animate-fade-up')
		})
	}
</script>

<Slide animate>
	<h1 class="text-5xl mb-6">What even are these things?</h1>
	<div class="grid grid-cols-1 h-[70vh] items-start">
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
			<span class="text-start">Bun</span>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="elysia js logo" src={elysia} />
			<span class="text-start">Elysia</span><span
				class="absolute right-0 translate-x-1/3"
				>{'<-Saved the best for last'}</span
			>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="turso logo" src={turso} />
			<span class="text-start">Turso</span>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="htmx logo" src={htmx} />
			<span class="text-start">HTMX</span>
		</div>
	</div>
</Slide>
<Slide animate on:in={animateCard} on:out={resetCard}>
	<div class="flex items-center gap-10">
		<img class="h-32 w-32 object-contain" alt="htmx logo" src={elysia} />
		<h1>Elysia</h1>
	</div>
	<p class="text-xl text-start max-w-prose mb-2">
		TypeScript framework supercharged by Bun with End-to-End Type Safety,
		unified type system and outstanding developer experience
	</p>
	<Code lang="jsx" style="font-size:14px;">
		{`
        import { Elysia } from 'elysia'
        import { html } from '@elysiajs/html'
        new Elysia()
            .use(html())
            .get('/jsx', () => (
                <html lang='en'>
                    <head>
                        <title>Hello World</title>
                    </head>
                    <body>
                        <h1>Hello World</h1>
                    </body>
                </html>
            ))
            .listen(3000)    
        `}
	</Code>
	<AuthorCard name="SaltyAom" image={saltyAom} />
</Slide>
<Slide animate>
	<div class="flex items-center gap-10 mb-6">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={elysia} />
		<h1>Elysia</h1>
	</div>
	<img src={elysiaSpeed} alt="elysia speed" />
</Slide>
<Slide animate>
	<div class="flex items-center gap-10 mb-6">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={elysia} />
		<h1>Elysia</h1>
	</div>
	<Step class="text-xl text-start max-w-prose mb-2">
		Provides amazing typesafe way to write backend code
	</Step>

	<Step class="text-xl text-start max-w-prose mb-2">
		Faster than your average Node.js framework
	</Step>

	<Step class="text-xl text-start max-w-prose mb-2">
		WinterCG Compliant, so it can run on any runtime, not just bun (Even in the
		browser!)
	</Step>

	<Step class="text-xl text-start max-w-prose mb-2">
		A strong ecosystem of plugins
	</Step>

	<Step class="text-xl text-start max-w-prose mb-2">"Just Return it!"</Step>
</Slide>
<Slide animate>
	<div class="flex items-center gap-10 mb-6">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={elysia} />
		<h1>Elysia</h1>
	</div>
	<img src={featureSheet} alt="elysia feature set" />
</Slide>
