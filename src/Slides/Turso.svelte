<script>
	import { Code, Slide, Step } from '@components'
	import bun from '../images/bun.svg'
	import elysia from '../images/elysia.svg'
	import turso from '../images/turso.svg'
	import htmx from '../images/htmx.png'
	import GlauberCosta from '../images/glauber_costa.png'
	import DejanMircevski from '../images/dejan_mircevski.png'
	import PekkaEnberg from '../images/pekka_enberg.png'
	import tursoUsage from '../images/turso_usage.jpg'

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
			<span class="text-start">Elysia</span>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="turso logo" src={turso} />
			<span class="text-start">Turso</span>
			<span class="absolute right-0 translate-x-1/3"
				>{'<-Next on the list'}</span
			>
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="htmx logo" src={htmx} />
			<span class="text-start">HTMX</span>
		</div>
	</div>
</Slide>
<Slide animate on:in={animateCard} on:out={resetCard}>
	<div class="flex items-center gap-10">
		<img class="h-32 w-32 object-contain" alt="htmx logo" src={turso} />
		<h1>Turso</h1>
	</div>
	<p class="text-xl text-start max-w-prose my-2">
		Turso is a cloud Database provider who promises The Fastest, Easiest,
		Cheapest Database in the World.
	</p>
	<!-- svelte-ignore a11y-media-has-caption -->
	<video
		playsinline
		muted
		autoplay
		loop
		src="https://videos.ctfassets.net/8fv5t5my8687/2yuGpbXlEU6XubDYNGFXlU/40906d1b37f1f9cbed3e7617276469a2/turso-map_2x.mp4"
		style="border-radius: 2%;"
		class="h-72"
	></video>

	<AuthorCard name="Glauber Costa" image={GlauberCosta} className="right-96" />
	<AuthorCard
		name="Dejan Mircevski"
		image={DejanMircevski}
		className="right-44"
	/>
	<AuthorCard name="Pekka Enberg" className="-right-5" image={PekkaEnberg} />
</Slide>
<Slide animate animateRestart>
	<h1 class="text-5xl mb-6 text-start">How?</h1>
	<Step class="text-start text-xl">
		Turso is built on top of a fork of our near and dear SQL database, SQLite.
		It's called LibSQL.
	</Step>
	<Step class="text-start text-xl">
		LibSQL is a fork of SQLite that has been modified with features like ALTER
		TABLE extensions, Random ROWID, WASM functions, Virtual Write ahead, and
		more. Unlike SQLite, LibSQL is truly OSS and accepts public contributions.
	</Step>
</Slide>
<Slide animate>
	<h1 class="text-5xl mb-6 text-start">How?</h1>
	<Step class="text-start text-xl my-3">
		SQLite is a dead simple single file database. It's fast (as far as
		read/writes on storage goes), and it's used in a lot of places. It's also
		not a client/server database, it's a file based database.
	</Step>
	<Step class="text-start text-xl my-3">
		This means that it's super cheap and easy to host. It's also super easy to
		scale. You can just copy the file to another server and you're done.
	</Step>
	<Step class="text-start text-xl my-3">
		This also allows Turso to do something that no other provider can do - run a
		cloud database together with your application in the same process,
		essentially giving you nanosecond reads.
	</Step>
</Slide>
<Slide animate>
	<h1 class="text-5xl mb-6 text-start">Nanosecond Reads with turso</h1>
	<Step class="text-start text-xl my-3">
		libSQL local replicas
		<a
			href="https://blog.turso.tech/microsecond-level-sql-query-latency-with-libsql-local-replicas-5e4ae19b628b"
			>(blog post)</a
		>
		replicates a copy of the remote database right next to where your application
		is running, so that you can query it as if you are querying a local SQLite database.
		Your database, now is right in the server instead of being in the cloud. Thus,
		you can query it in nanoseconds.
		<img
			alt="libSQL local replicas query graph"
			src="https://res.cloudinary.com/djytfiogl/image/upload/c_lfill,g_center,w_768/v1696836250/turso-blog/articles_dev/hrdrwauxpwxoxsa1gb7s.webp"
		/>
	</Step>
</Slide>
<Slide animate>
	<h1 class="text-5xl mb-6 text-start">Why Turso?</h1>
	<p class="text-start text-xl">
		They also give you three global replicated locations (like different servers
		across the globe you can replicate the same data), 500 databases, 9GB of
		storage, 1B rows read, 25M row Writes, etc. Just sayin.
	</p>
	<img src={tursoUsage} alt="turso usage" class="mt-8 object-contain" />
</Slide>
