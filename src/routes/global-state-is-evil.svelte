<script context="module">
    import { name as name3 } from './_stores'
    function sleep(ms) {
        return new Promise(resolve => setTimeout(resolve, ms));
    }
	export async function preload({ params, query }) {
        // this is only possible because the store is not reset
        // on a per-request basis.
        for (var i=0; i<60; i++) {
            name3.set(`evil-${i}`)
            await sleep(1000);
        }
	}
</script>

<h1>This is evil.</h1>
