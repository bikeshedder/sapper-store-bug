<script context="module">
	import { name as name3 } from './_stores'
	export function preload({ params, query }) {
        // this is only possible because the store is not reset
        // on a per-request basis.
	    name3.set(params.name)
		return { name: params.name }
	}
</script>

<script>
	export let name;

	import { stores } from '@sapper/app'
	const name1 = stores().name
	name1.set(name)

    import { getContext } from 'svelte'
    import { NAME2_CTX } from './_layout.svelte'
	const name2 = getContext(NAME2_CTX)
	name2.set(name)
</script>

<h2>routes/[name].svelte :: stores().name = {$name1}</h2>
<h2>routes/[name].svelte :: getContext('name') = {$name2}</h2>
<h2>routes/[name].svelte :: _stores.name = {$name3} </h2>
