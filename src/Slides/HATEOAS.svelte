<script lang="ts">
	import { Code, Slide, Step } from '@components'
</script>

<Slide animate animateId="HATEOAS">
	<h1 class="text-9xl font-bold text-start">HATEOAS</h1>
</Slide>

<Slide animate animateId="HATEOAS">
	<h1 class="text-6xl font-bold text-start mb-8">HATEOAS</h1>
	<h2 class="text-3xl font-bold text-start mb-8">
		Hypermedia As The Engine Of Application State
	</h2>
	<p class="text-xl text-start max-w-prose">
		<span class="text-slate-400">From Wikipedia:</span>With HATEOAS, a client
		interacts with a network application whose application servers provide
		information dynamically through hypermedia. A REST client needs little to no
		prior knowledge about how to interact with an application or server beyond a
		generic understanding of hypermedia.
	</p>
</Slide>
<Slide animate animateId="HATEOAS">
	<h1 class="text-6xl font-bold text-start mb-8">HATEOAS</h1>
	<Code lang="json" class="text-xs">
		{`
            {
                "account": {
                    "account_number": 12345,
                    "balance": {
                        "currency": "usd",
                        "value": 100.00
                    },
                    "links": {
                        "deposits": "/accounts/12345/deposits",
                        "withdrawals": "/accounts/12345/withdrawals",
                        "transfers": "/accounts/12345/transfers",
                        "close-requests": "/accounts/12345/close-requests"
                    }
                }
            }`}
	</Code>
</Slide>
<Slide animate animateId="HATEOAS">
	<h1 class="text-6xl font-bold text-start mb-8">HATEOAS</h1>
	<p class="text-start text-2xl max-w-prose mb-3">
		HTMX says that this way of using HATEOAS is inferior, and gives a more
		easier idea, which simplifies web development in general. That is, replacing
		JSON with HTML as the hypermedia format.
	</p>
	<Code lang="html">
		{`
        <html>
          <body>
            <div>Account number: 12345</div>
            <div>Balance: $100.00 USD</div>
            <div>Links:
               <a href="/accounts/12345/deposits">deposits</a>
               <a href="/accounts/12345/withdrawals">withdrawals</a>
               <a href="/accounts/12345/transfers">transfers</a>
               <a href="/accounts/12345/close-requests">close-requests</a>
            </div>
          <body>
        </html>
        `}
	</Code>
</Slide>
<Slide animate animateId="HATEOAS">
	<h1 class="text-6xl font-bold text-start mb-8">HATEOAS</h1>
	<p class="text-start text-2xl max-w-prose mb-3">
		This way, the data format itself turns into the view that we want, and at
		the same time, the view is also an exact representation of the server state,
		without any need for client side state management.
	</p>
</Slide>
<Slide animate animateId="HATEOAS">
	<h1 class="text-6xl font-bold text-start mb-8">HATEOAS</h1>
	<p class="text-start text-2xl max-w-prose mb-3 italic">
		"Bro, we already used to do that... it was called templates, we stopped
		using it cuz it was difficult to write interactive apps with it..." - 🤓
	</p>
	<Step class="text-start text-2xl mb-3">
		Correct. the static HTML that we used to write, could not be interactive
		without a lot of client side JavaScript. This gave birth to things like
		jQuery,jQueryUI, Bootstrap, etc, and we eventually moved to Single Page Apps
		(SPA) with frameworks like Angular, React, Vue, etc.
	</Step>

	<Step class="text-start text-2xl mb-3">
		HTMX Solves this issue from the other side. By adding data fetching and
		interaction capabilities to HTML, we can now write interactive apps with
		just HTML, and a little bit of JavaScript.
	</Step>
</Slide>
