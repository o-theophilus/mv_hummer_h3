<script context="module">
	export function load({ error, status }) {
		return {
			props: {
				status,
				error,
			},
		};
	}
</script>

<script>
	export let status;
	export let error;
</script>

<h1>{status} {error.name}</h1>
<p>{error.message}</p>
Back to<a href="/">Home</a>
