<script context="module">
	export const NAME2_CTX = {}
</script>

<script>
	import { setContext } from 'svelte'
	import { writable } from 'svelte/store'
	import { stores } from '@sapper/app'

	export const name1 = writable()
	stores().name = name1

	export const name2 = writable()
	setContext(NAME2_CTX, name2)

	import { name as name3 } from './_stores'
</script>

<main>
	<h2>routes/_layout.svelte :: stores().name = {$name1}</h2>
	<h2>routes/_layout.svelte :: getContext('name') = {$name2}</h2>
	<h2>routes/_layout.svelte :: _stores.name = {$name3} </h2>
	<slot></slot>
</main>
