<script lang="ts">
	import { Code, Presentation, Slide, Step } from '@components'
	import bun from './images/bun.svg'
	import elysia from './images/elysia.svg'
	import turso from './images/turso.svg'
	import htmx from './images/htmx.png'
	import Htmx from './Slides/Htmx.svelte'
	import Turso from './Slides/Turso.svelte'
	import Bun from './Slides/Bun.svelte'

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

<Presentation>
	<div class="absolute bottom-0 right-0 w-min h-min">
		<a
			href="https://github.com/arjunindia"
			class="flex items-center gap-2 text-xl text-slate-400 z-50"
			><svg
				xmlns="http://www.w3.org/2000/svg"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				><path
					fill="currentColor"
					d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
				/></svg
			>@arjunindia</a
		>
	</div>
	<Slide animate>
		<p class="font-bold text-8xl">The BETH Stack</p>
		<div class="flex mt-8">
			<img class="flex-1 h-32 object-contain" alt="bun logo" src={bun} />
			<img
				class="flex-1 h-32 object-contain"
				alt="elysia js logo"
				src={elysia}
			/>
			<img class="flex-1 h-32 object-contain" alt="turso logo" src={turso} />
			<img class="flex-1 h-32 object-contain" alt="htmx logo" src={htmx} />
		</div>
	</Slide>

	<Slide animate>
		<p class="font-bold text-8xl">The BETH Stack</p>
		<div class="flex mt-8">
			<img class="flex-1 h-32 object-contain" alt="bun logo" src={bun} />
			<img
				class="flex-1 h-32 object-contain"
				alt="elysia js logo"
				src={elysia}
			/>
			<img class="flex-1 h-32 object-contain" alt="turso logo" src={turso} />
			<img class="flex-1 h-32 object-contain" alt="htmx logo" src={htmx} />
		</div>
		<p class="text-xl mt-10">
			Building web apps with amazing performance without compromizing DX.
		</p>
	</Slide>

	<Slide animate>
		<h1 class="text-5xl mb-6">What even are these things?</h1>
		<div class="grid grid-cols-1 h-[70vh] items-start">
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
				<span class="text-start">Bun</span>
			</div>
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img
					class="h-32 w-32 object-contain"
					alt="elysia js logo"
					src={elysia}
				/>
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

	<Htmx />
	<Slide animate>
		<h1 class="text-5xl mb-6">What even are these things?</h1>
		<div class="grid grid-cols-1 h-[70vh] items-start">
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
				<span class="text-start">Bun</span>
			</div>
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img
					class="h-32 w-32 object-contain"
					alt="elysia js logo"
					src={elysia}
				/>
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

	<Turso />

	<Slide animate>
		<h1 class="text-5xl mb-6">What even are these things?</h1>
		<div class="grid grid-cols-1 h-[70vh] items-start">
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img class="h-32 w-32 object-contain" alt="bun logo" src={bun} />
				<span class="text-start">Bun</span>
			</div>
			<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
				<img
					class="h-32 w-32 object-contain"
					alt="elysia js logo"
					src={elysia}
				/>
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

	<Bun />
</Presentation>
