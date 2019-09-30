<script>
	import { stores } from '@sapper/app'
	const name1 = stores().name
	import { getContext } from 'svelte'
    import { NAME2_CTX } from './_layout.svelte'
	const name2 = getContext(NAME2_CTX)
	import { name as name3 } from './_stores'
</script>

<h2>routes/index.svelte :: stores().name = {$name1}</h2>
<h2>routes/index.svelte :: getContext('name') = {$name2}</h2>
<h2>routes/index.svelte :: _stores.name = {$name3} </h2>
