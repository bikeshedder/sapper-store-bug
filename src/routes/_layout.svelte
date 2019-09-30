<script>
	import { setContext } from 'svelte'
	import { writable } from 'svelte/store'
	import { stores } from '@sapper/app'

	export const foo = writable()
	stores().foo = foo

	export const bar = writable()
	setContext('bar', bar)
</script>

<main>
	<h2>_layout.svelte :: foo = {$foo}</h2>
	<h2>_layout.svelet :: bar = {$bar}</h2>
	<slot></slot>
</main>
