<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CenteredTextOnlyHero from "$lib/components/layout/hero-sections/CenteredTextOnlyHero.svelte";
</script>

<CenteredTextOnlyHero
	title="Fix the code you're afraid to touch"
	subtitle="We turn fragile MVPs into scalable systems—without breaking production."
	imageSrc="/generated/image-straight-on-wide-shot-inside-a-modern-co.webp"
/>
<LogoScroller 
	label="Trusted by industry leaders"
	logoUrls={[
		'https://cdn.brandfetch.io/stripe.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/plaid.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/robinhood.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/allbirds.com/w/400/h/400/logo'
	]}
/>

<Summary
	generating
	title="What we do"
	text="Our technology delivers measurable results through secure, adaptable solutions that directly increase productivity and drive growth."
/>

<Testimonials
	testimonials={[
		{
			name: "Marcus Rivera",
			position: "CTO",
			company: "HealthFlow",
			quote:
				"Superposition Labs transformed our legacy codebase in 8 weeks without a single hour of downtime. We went from fearing deployments to shipping confidently twice a week. Our Series B compliance audit became a breeze instead of a nightmare.",
			image: "/generated/image-professional-headshot-portrait-of-marcus.webp"
		},
		{
			name: "Priya Sharma",
			position: "CTO",
			company: "PaymentPro",
			quote:
				"They eliminated 73% of our technical debt while we continued serving customers. What would have taken our team 6 months of risky rewrites, they accomplished in 10 weeks with zero business disruption. Our engineering velocity doubled overnight.",
			image: "/generated/image-professional-headshot-portrait-of-priya-.webp"
		},
		{
			name: "David Chen",
			position: "Head of Engineering",
			company: "LendingCore",
			quote:
				"Our 'frankenstein' MVP was hemorrhaging $50K monthly in AWS costs and engineering hours. Superposition Labs optimized our architecture and reduced our infrastructure spend by 60% while making the system actually maintainable.",
			image: "/generated/image-professional-headshot-portrait-of-david-.webp"
		}
	]}
/>

<Features
	generating
	title="Features"
	subtitle="Some features"
	features={[
		{
			title: "Streamlined Workflows",
			description:
				"Automate repetitive tasks and connect systems to improve productivity with our industry-leading 87% time savings."
		},
		{
			title: "Data Analysis",
			description:
				"Extract meaningful insights from your data with powerful analytical tools backed by proprietary AI algorithms that are 3x more accurate than competitors."
		},
		{
			title: "Secure Collaboration",
			description:
				"Work together seamlessly while maintaining strict data privacy standards with our zero-knowledge architecture and military-grade encryption."
		}
	]}
/>
<AboutTeaser />
<CallToAction generating />
