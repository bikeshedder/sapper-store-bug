<script context="module">
	export function preload({ params, query }) {
		return { name: 'borat' }
	}
</script>

<script>
	export let name;

	import { stores } from '@sapper/app'
	import { getContext } from 'svelte'

	const foo = stores().foo
	foo.set(name)

	const bar = getContext('bar')
	bar.set(name)
</script>

<h2>routes/index.svelte :: $foo = {$foo}</h2>
<h2>routes/index.svelte :: $bar = {$bar}</h2>
