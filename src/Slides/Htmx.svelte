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
		</div>
		<div class="grid grid-cols-2 mx-auto gap-10 justify-start items-center">
			<img class="h-32 w-32 object-contain" alt="htmx logo" src={htmx} />
			<span class="text-start">HTMX</span>
			<span class="absolute right-0 translate-x-1/3"
				>{'<-Lets start with this guy'}</span
			>
		</div>
	</div>
</Slide>

<Slide animate on:in={animateCard} on:out={resetCard}>
	<div class="flex items-center gap-10">
		<img class="h-32 w-32 object-contain" alt="htmx logo" src={htmx} />
		<h1>HTMX</h1>
	</div>
	<p class="text-xl text-start max-w-prose mb-2">
		htmx is a library that allows you to access modern browser features directly
		from HTML, rather than using javascript.
	</p>
	<Code lang="html">
		{`
        <button
            hx-post="/clicked"
            hx-trigger="click"
            hx-target="#parent-div"
            hx-swap="outerHTML"
        >
            Click Me!
        </button>`}
	</Code>
	<AuthorCard name="Big Sky Software" image={bigskysoftware} />
</Slide>
<Slide>...What? Why??</Slide>
<Slide animate>
	<div class="flex gap-10 items-center">
		<p class="flex-1 text-xl text-start max-w-prose mb-2">
			You might think that HTMX is just a gimmick, a small library that won't
			really be `That good`, useless `like jQuery`, doesn't scale for my
			project, wouldn't work for what I'm doing, etc on the first look. But, the
			idea it promotes is much more interesting, and simplifies building modern
			UIs in a way that is much more intuitive.
			<br />
			<br />
			No, it's not another javascript framework either.
		</p>
		<img
			src={htmx_thoughts}
			class="flex-1 object-contain"
			alt="htmx thoughts"
		/>
	</div>
</Slide>
<Slide animate>
	<h1>The problem with the current model of web development</h1>
</Slide>

<Slide animate>
	<h1 class="text-start">
		The problem with the current model of web development
	</h1>
	<p class="text-xl text-start my-8">
		In modern web apps, we usually follow the <em>`AJAX/JSON Pattern.`</em> This
		was popularized by the rise of AJAX, and the rise of JSON as a data format, with
		libraries like jQuery and Backbone.js.
	</p>

	<Step class="text-start text-2xl mb-3">
		&gt; In the server, we request data (from a database likely) and create a
		data representation.</Step
	>
	<Step class="text-start text-2xl mb-3">
		&gt; Then we encode/serialize that into JSON/XML.</Step
	>
	<Step class="text-start text-2xl mb-3">
		&gt; We send that to the client, where we decode/deserialize that into a
		JavaScript object.
	</Step>
	<Step class="text-start text-2xl mb-3">
		&gt; We then use that data to update the DOM, and add event listeners to
		elements.
	</Step>
</Slide>
<Slide animate>
	<h1 class="text-start">
		The problem with the current model of web development
	</h1>
	<p class="text-xl text-start my-8">This model has to deal with:</p>
	<Step class="text-start text-2xl mb-3">
		&gt; Data serialization/deserialization on both the server and client.
	</Step>
	<Step class="text-start text-2xl mb-3">
		&gt; Having to write the same logic twice for the structure of the data, and
		the logic to manipulate it, basically doubling the amount of code you have
		to write.
	</Step>
	<Step class="text-start text-2xl mb-3"
		>&gt; DOM manipulation to insert data from the server</Step
	>
	<Step class="text-start text-2xl mb-3"
		>&gt; Event handling and fetching the data itself from the server</Step
	>
	<Step class="text-start text-2xl mb-3">&gt; Error handling</Step>
	<Step class="text-start text-2xl mb-3"
		>&gt; Keeping the client state in sync with that of the server</Step
	>
	<Step class="text-start text-2xl mb-3">&gt; And more...</Step>
</Slide>
<Slide animateRestart animate>
	<h1>Some solutions for this problem</h1>
</Slide>
<Slide animate>
	<h1 class="text-start">Some solutions for this problem</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		GraphQL - A query language for your API, which allows you to specify the
		data you want to get from the server, and the server will return that data
		in the same structure.
		<br />
		<br />
		This solves the problem of having to write the same logic twice, but it does
		not solve the problem of having to write the logic to manipulate the data, and
		the logic to fetch the data. GraphQL is also a very complex system, and comes
		with a lot of overhead and complexity.
	</div>
</Slide>
<Slide animate>
	<h1 class="text-start">Some solutions for this problem</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		React Server Components (RSC) - A new feature in React that allows you to
		write React components on ther server and send them to the client, where
		they will be hydrated and rendered. This solves majority of your problems,
		and might be a great choice if you are already using React/Next.js.
		<br />
		<br />
		However, this is still in development, and most frameworks don't have support
		for them except for Next.js, which is infamous for bad support outside Vercel.
	</div>
</Slide>
<Slide animate>
	<h1 class="text-start">Some solutions for this problem</h1>
	<br />
	<Step class="text-start text-2xl mb-3">
		Thankfully, we already have a solution for this problem, and it's been
		around for a long time. It's called <em>`HTML`</em>.
	</Step>
	<Step class="text-start text-2xl mb-3">
		What we forget is that HTML is a hypermedia format, and it's a very good one
		at that. Especially considering what browsers can do with it.
	</Step>
	<Step class="text-start text-2xl mb-3">
		The problem is that we don't use HTML as a hypermedia format, we use it as a
		static document format, and use JavaScript to manipulate it. We are too used
		to the AJAX/JSON pattern.
	</Step>
</Slide>
<HATEOAS />
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
</Slide>

<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		HTMX is a library that allows you to access modern browser features directly
		from HTML, rather than using javascript.
		<br />
		<br />
		It does this by adding attributes to HTML elements, which are called
		<em>`HX Attributes`</em>.
		<br />
		<br />
		These attributes are prefixed with <em>`hx-`</em>, and are used to specify
		the behavior of the element.
	</div>
</Slide>

<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		Let's take the example of a simple Like button.
		<br />
		The user needs to be able to click the button, and like the post. When the user
		clicks the button, it needs to inform the server that the user has liked the
		post, and the server should update the DB. While the client should show that
		the like has been registered to the user, by maybe changing the color/text of
		the button.
	</div>
	<Step class="text-start text-2xl mb-3">
		In traditional HTML with templates, we would have to either write a lot of
		client side javascript from scratch, or use forms to submit the event to a
		server, which would then cause the webpage to reload, causing bad DX.
	</Step>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		Let's take the example of a simple Like button.
	</div>
	<div class="text-start text-2xl mb-3">
		In a modern web app, like with React, the client side javascript is now a
		lot more convenient to write. But that doesn't mean it's simple.
	</div>
	<p class="text-start text-xl">On the server:</p>
	<Code lang="ts">
		{`
        new Server()
            .post('/like/:postId', () => {
                try{
                    checkAuth();
                    likePost(postId);
                    return { success: true,likeCount: getLikeCount(postId) }
                } catch(e) {
                    return { error: e.message }
                }
            })
            .listen(8080)
        `}
	</Code>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		Let's take the example of a simple Like button.
	</div>
	<p class="text-start text-xl">
		Then the client (using react here) will be something like :
	</p>
	<Code lang="ts">
		{`
        const LikeButton = ({postId}) => {
            const [likeCount, setLikeCount] = useState(0);
            const [liked, setLiked] = useState(false);
            const likePost = async () => {
                const res = await fetch(\`/like/\${postId}\`, { method: 'POST' });
                const data = await res.json();
                setLikeCount(data.likeCount);
                setLiked(true);
            }
            return (
                <button onClick={likePost} className={liked ? 'liked' : ''}>
                    <span>{likeCount}</span>
                </button>
            )
        }
        `}
	</Code>
</Slide>

<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		Let's take the example of a simple Like button.
	</div>
	<p class="text-start text-xl text-red-400">
		Oops, forgot the types, so we got a type error. Also got a bunch of
		undefined. TypeScript IS superior.
	</p>
	<Code lang="ts">
		{`
        const LikeButton = ({postId}: {postId: string}) => {
            const [likeCount, setLikeCount] = useState(0);
            const [liked, setLiked] = useState(false);
            const likePost = async () => {
                const res = await fetch(\`/like/\${postId}\`, { method: 'POST' });
                const data : { likeCount: number } = await res.json();
                setLikeCount(data.likeCount);
                setLiked(true);
            }
            return (
                <button onClick={likePost} className={liked ? 'liked' : ''}>
                    <span>{likeCount}</span>
                </button>
            )
        }
        `}
	</Code>
</Slide>

<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<div class="text-start text-2xl mb-3">
		Let's take the example of a simple Like button.
	</div>
	<p class="text-start text-xl text-red-600">
		Oops, forgot to handle errors, skill issue ig
	</p>
	<Code lang="ts">
		{`
        const LikeButton = ({postId}: {postId: string}) => {
            const [error, setError] = useState('');
            const [likeCount, setLikeCount] = useState(0);
            const [liked, setLiked] = useState(false);
            const likePost = async () => {
                try {
                    const res = await fetch(\`/like/\${postId}\`, { method: 'POST' });
                    const data : { likeCount: number, error: string } = await res.json();
                    if (data.error) {
                        setError(data.error);
                        return;
                    }
                    setLikeCount(data.likeCount);
                    setLiked(true);
                } catch(e) {
                    setError(e.message);
                }
                setLikeCount(data.likeCount);
            }
            return (
                <>
                    {error && <div>{error}</div>}
                    <button onClick={likePost} className={liked ? 'liked' : ''}>
                        <span>{likeCount}</span>
                    </button>
                </>
            )
        }
        `}
	</Code>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<p class="text-start">
		And this is just a simple like button. Imagine if you had to do this for a
		whole app.
	</p>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<p class="text-start">Now let's use HTMX to do the same thing.</p>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<p class="text-start text-base">The client at the start looks like this.</p>
	<Code lang="ts">
		{`
        <button
            hx-post="/like/2"
            hx-trigger="click"
            hx-swap="outerHTML"
        >
            <span>
                0    
            </span>
        </button>
        `}
	</Code>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<p class="text-start text-base">
		We can just return how that element looks after update. Notice that error
		handling can be done right here.
	</p>
	<Code lang="ts" style="font-size:16px!important">
		{`
        new Server()
            .post('/like/:postId', () => {
                try{
                    checkAuth();
                    likePost(postId);
                    return \`
                        <button hx-post="/like/\${postId}" hx-trigger="click" hx-swap="outerHTML">
                            <span>
                                \${getLikeCount(postId)}    
                            </span>
                        </button>\`
                } catch(e) {
                    return \`
                        <button hx-post="/like/\${postId}" hx-trigger="click" hx-swap="outerHTML">
                            <span>
                                \${getLikeCount(postId)}    
                            </span>
                        </button>
                        <div>\${e.message}</div>\`
                }
            })
            .listen(8080)
        `}
	</Code>
</Slide>
<Slide animate>
	<h1 class="text-start">Why use HTMX?</h1>
	<br />
	<Step class="text-start text-xl mb-4">
		&gt; HTMX allows you to specify where the response should be inserted. Even
		from the server.
	</Step>
	<Step class="text-start text-xl mb-4">
		&gt; HTMX allows you to trigger client side routing from the server.
	</Step>
	<Step class="text-start text-xl mb-4">
		&gt; HTMX allows you to easily perform things like loading states with just
		one attribute and CSS class.
	</Step>
	<Step class="text-start text-xl mb-4">
		&gt; HTMX allows you to select part of the data you recieve from the server
		and only insert that.
	</Step>
	<Step class="text-start text-xl mb-4">
		&gt; HTMX allows you to perform client side validation, and show errors from
		the server. And it's very easy too, by building on top of the normal HTML
		form validation.
	</Step>
	<Step class="text-start text-xl mb-4">
		&gt; HTMX even has features for things like infinite scrolling, prefetching,
		confirmation alerts, View Transitions, and more.
	</Step>
	<Step class="text-start text-2xl">
		And all of this is done with just ONE DEPENDENCY!
	</Step>
</Slide>
<Slide>
	<h1 class="text-start text-3xl">
		BETH Stack is not the only way to use HTMX. You don't need to use Javascript
		on the server either. Anything works really.
	</h1>
	<p class="text-base text-start my-8">
		One of the popular ways to use HTMX is with Go, which I like to call `GOTH
		Stack`.
	</p>
	<Step class="text-base text-start my-8">
		It also plays well with languages like Python, Ruby, PHP, Rust, Elixir,
		Java, etc.
	</Step>
	<Step class="text-base text-start my-8">
		You can even use it with frameworks like Next.js, or even with React, Vue,
		Svelte, etc. If you want.
		<br />
		Astro even added support for partial output just for HTMX support.
	</Step>
</Slide>
