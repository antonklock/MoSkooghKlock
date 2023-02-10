<script lang="ts">
	import TestComponent from '../Components/TestComponent.svelte';

	const name = 'MoSkooghKlock';
</script>

<h1>Welcome to {name}</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

{#each Array(3) as comp}
	<TestComponent />
{/each}
