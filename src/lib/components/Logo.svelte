<script lang="ts">
	import type { HTMLAttributes } from "svelte/elements";
	const props: HTMLAttributes<SVGSVGElement> = $props();
</script>

<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="" {...props}>
	<!-- Represents overlapping layers/systems - perfect for the "superposition" concept -->
	<rect x="3" y="3" width="10" height="10" rx="2" fill="currentColor" opacity="0.3" />
	<rect x="6" y="6" width="10" height="10" rx="2" fill="currentColor" opacity="0.6" />
	<rect x="9" y="9" width="10" height="10" rx="2" fill="currentColor" />
	<!-- Small connecting element representing the "labs" aspect -->
	<circle cx="8" cy="8" r="1.5" fill="currentColor" />
</svg>
