<script>
	let workaround = setInitialClassState.toString();

	function setInitialClassState() {
		// does something
	}
</script>

<svelte:head>
	<!-- This causes the new eslint-plugin-svelte to throw a parsing error -->
	{@html `<script nonce="%sveltekit.nonce%">(${setInitialClassState.toString()})();</script>`}

	<!-- This is works  -->
	{@html `<script nonce="%sveltekit.nonce%">(` + workaround + `)();</script>`}
</svelte:head>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
