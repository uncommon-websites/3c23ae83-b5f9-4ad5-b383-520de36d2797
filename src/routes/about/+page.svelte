<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Practical expertise",
			description: "We've seen it all in regulated industries. No theoretical solutions, just battle-tested approaches that work in the real world."
		},
		{
			title: "Startup empathy",
			description: "We understand the pressure-cooker environment. We're here to help, not judge the 'vibe-coded' reality of fast-moving startups."
		},
		{
			title: "No-nonsense methodology",
			description: "Structured, incremental refactoring that maintains business continuity. We're the cleanup crew that actually gets things done."
		}
	];
</script>

<SecondaryHero
	title="Clean code, without the chaos"
	subtitle="Incremental refactoring that keeps you moving"
	imageSrc="/generated/image-photorealistic-candid-scene-of-senior-so.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"We started in 2018 with a simple goal: make helpful tech that people actually need. While many chase profits, we chose to do things differently.",
		"Beyond making good products, we care about doing the right thing, being kind to our planet, and making sure everyone can use what we build. That's our compass.",
		"From day one, we've asked ourselves: 'Does this actually help people?' This question gets us through tough calls and shapes who we are. We're playing the long game here.",
		"We think about how our work affects real people's lives. We build tech that brings people together, keeps your information safe, and treats everyone fairly. When we stick to these basics, good things happen."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- Team positioning section - focusing on experience rather than individuals -->
<section class="section-py section-px">
	<div class="container mx-auto max-w-4xl text-center">
		<h2 class="text-h2 mb-4">Senior engineers who've seen it all</h2>
		<p class="text-body text-gray-600 dark:text-gray-400 mb-8">
			Our team consists of senior engineers and architects with deep experience in regulated industries. 
			We've navigated the pressures of fintech compliance audits, healthtech security requirements, 
			and the unique challenges of scaling startup systems under intense business pressure.
		</p>
		<p class="text-body text-gray-600 dark:text-gray-400">
			We understand the reality of "vibe-coded" applications and the technical debt that accumulates 
			when you're moving fast to capture market opportunities. That's exactly why we're here - 
			to be your experienced cleanup crew.
		</p>
	</div>
</section>

<!-- CTA Section -->
<CallToAction
	title="Stop letting technical debt slow you down"
	subtitle="Ready to scale with confidence?"
	description="Join Series A and Series B startups who've transformed their fragile codebases into production-ready systems without the chaos of complete rewrites. Let's rebuild trust in your technology."
/>
