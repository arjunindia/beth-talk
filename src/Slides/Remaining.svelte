<script>
	import pilcrow from '../images/pilcrow.png'
	import bigskysoftware from '../images/bigskysoftware.png'
	import drizzleteam from '../images/drizzleteam.jpg'
	import { Code, Slide, Step } from '@components'
	import AuthorCard from '../components/AuthorCard.svelte'
	const animateCard = () => {
		document.querySelectorAll('.card').forEach((card) => {
			card.classList.add('animate-fade-up')
			setTimeout(() => {
				card.classList.remove('animate-fade-up')
			}, 1000)
		})
	}
</script>

<Slide animate>
	<h1 class="text-start mb-4">
		That's not everything. These are also part of this stack
	</h1>
	<Step class="text-start mb-4 text-xl"
		>UnoCSS - Atomic CSS Engine (Or just use tailwind)</Step
	>
	<Step class="text-start mb-4 text-xl"
		>Lucia Auth - Complex authentication made simple</Step
	>
	<Step class="text-start mb-4 text-xl"
		>HyperScript - funny javascript (`on click increment :x then put result into
		me`)</Step
	>
	<Step class="text-start mb-4 text-xl"
		>Drizzle ORM - An ORM that you would hate less, probably</Step
	>
</Slide>
<Slide on:in={animateCard}>
	<h1 class="text-start">Lucia Auth</h1>
	<p class="text-start text-xl my-4">
		Lucia is an auth library for TypeScript that abstracts away the complexity
		of handling users and sessions. It works alongside your database to provide
		an API that's easy to use, understand, and extend.
	</p>
	<Code lang="ts" style="font-size:14px;">
		{`
        import { lucia } from "lucia";
        import { web } from "lucia/middleware";
        export const auth = lucia({
        	adapter: ADAPTER,
        	env: "DEV", // "PROD" for production
        	middleware: web(),
        	sessionCookie: {
        		expires: false
        	},
        	getUserAttributes: (data) => {
        		return {
        			username: data.username
        		};
        	}
        });
        export type Auth = typeof auth;
        `}
	</Code>
	<AuthorCard image={pilcrow} name="pilcrowOnPaper" />
</Slide>
<Slide on:in={animateCard}>
	<h1 class="text-start">HyperScript</h1>
	<p class="text-start text-xl my-4">
		An easy & approachable language for modern web front-ends...?
	</p>
	<Code lang="ts" style="font-size:14px;">
		{`
        on pointerdown
            repeat until event pointerup
                set rand to Math.random() * 360
                transition
                    *background-color
                    to \`hsl($rand 100% 90%)\`
                    over 250ms
        end
        `}
	</Code>
	<AuthorCard image={bigskysoftware} name="Big Sky Software" />
</Slide>
<Slide on:in={animateCard}>
	<h1 class="text-start">Drizzle ORM</h1>
	<p class="text-start text-xl my-4">
		Drizzle ORM is a headless TypeScript ORM with a head 🐲 <br /> It looks and feels
		simple, performs on day 1000 of your project, lets you do things your way, and
		is there when you need it.
	</p>
	<Code lang="ts">
		{`
        import { eq, lt, gte, ne } from 'drizzle-orm';
 
        await db.select().from(users).where(eq(users.id, 42));
        await db.select().from(users).where(lt(users.id, 42));
        await db.select().from(users).where(gte(users.id, 42));
        await db.select().from(users).where(ne(users.id, 42));
        `}
	</Code>
	<AuthorCard image={drizzleteam} name="Drizzle Team" />
</Slide>
