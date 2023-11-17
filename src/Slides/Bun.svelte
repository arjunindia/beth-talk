<script>
	import { Code, Slide, Step } from '@components'
	import bun from '../images/bun.svg'
	import elysia from '../images/elysia.svg'
	import turso from '../images/turso.svg'
	import htmx from '../images/htmx.png'
	import bigskysoftware from '../images/bigskysoftware.png'
	import htmx_thoughts from '../images/htmx-thoughts.jpeg'
	import AuthorCard from '../components/AuthorCard.svelte'
	import HATEOAS from './HATEOAS.svelte'
	import { animate } from '@motion'
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
			<span class="absolute right-0 translate-x-1/3"
				>{'<-Time for some javascript😄'}</span
			>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="elysia js logo" src={elysia} />
			<span class="text-start">Elysia</span>
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
<Slide animate>
	<div class="flex items-center">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
		<h1>Bun</h1>
	</div>
	<p class="text-start text-2xl">
		Bun is a a fast JavaScript runtime designed as a drop-in replacement for
		Node.js. It's written in Zig and powered by JavaScriptCore under the hood,
		dramatically reducing startup times and memory usage.
	</p>
	<br />

	<Step class="text-start text-2xl">
		Oops, I meant, Bun is an all in one toolkit of Javascript tooling.
		Including:
		<br />
		<br />
		The Runtime
		<br />
		<br />
		The Package Manager
		<br />
		<br />
		The Bundler
		<br />
		<br />
		The Compiler
		<br />
		<br />
		The Package Executor
		<br />
		<br />
		The Test Runner
	</Step>
</Slide>
<Slide animate>
	<div class="flex items-center">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
		<h1>Bun</h1>
	</div>
	<p class="text-start text-2xl">
		Bun has some amazing features that we gracefully can use for our stack apart
		from just the performance boost it provides.
		<br />
		<br />
		Bun can run TypeScript without needing any compilation/Transpilation.
		<br />
		<br />
		Bun can also run JSX/TSX files like that - Which is also crucial.
	</p>
</Slide>
<Slide animate>
	<div class="flex items-center">
		<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
		<h1>Bun</h1>
	</div>
	<p class="text-start text-2xl">
		The following code cannot be directly run through node, but is perfectly
		fine in Bun as long as you provide what you need it to transpile to on the
		config file. To use the following code, you need to use something like TSC
		to transpile it to JS to run on node, or use something like tsx to run it
		with some overhead.
	</p>
	<Code lang="tsx">
		{`
        function Component(props: {message: string}) {
          return (
            <body>
              <h1 style={{color: 'red'}}>{props.message}</h1>
            </body>
          );
        }

        console.log(<Component message="Hello world!" />);
        `}
	</Code>
</Slide>
