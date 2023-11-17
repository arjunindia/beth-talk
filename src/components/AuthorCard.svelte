<script lang="ts">
	export let name: string
	export let image: string
	export let className = ''
</script>

<div
	class={`card animate-delay-500 absolute rounded-xl bottom-0 right-0 flex items-start flex-col gap-3 bg-background px-6 py-4 border border-slate-700 shadow-xl ${className}`}
>
	<span class="text-xl text-start">Created by</span>
	<img
		class="h-32 w-32 object-contain"
		alt="big sky software logo"
		src={image}
	/>
	<span class="text-xl text-start">{name}</span>
</div>
