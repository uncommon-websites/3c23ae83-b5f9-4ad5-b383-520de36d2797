<script lang="ts">
	// Types
	import type { HTMLAttributes } from "svelte/elements";
	import { navigation } from "$lib/navigation";

	// Components
	import { CONFIG } from "$lib/content";
	import Signature from "./Signature.svelte";

	// Props
	const props: HTMLAttributes<HTMLElement> = $props();
</script>

<footer
	class="inset-x-0 bottom-0 -z-10 grid overflow-hidden bg-background"
	aria-labelledby="footer-heading"
	{...props}
>
	<div
		class="section-px relative z-10 container mx-auto pt-16 pb-8"
	>
		<!-- Main footer content -->
		<div class="grid gap-12 lg:grid-cols-4 lg:gap-16">
			<!-- Company info -->
			<div class="lg:col-span-2">
				<div class="text-headline flex items-center gap-4 mb-6">
					<div class="text-headline">
						{CONFIG.companyName}<sup
							class="ml-0.5 align-super text-[.25em]"
							style="color: var(--color-foreground);">TM</sup
						>
					</div>
				</div>
				<p class="text-muted-foreground text-sm leading-relaxed max-w-md mb-6">
					Transforming fragile startup codebases into production-ready systems through incremental refactoring that preserves business continuity while eliminating technical debt.
				</p>
				<div class="text-sm space-y-2">
					<div class="flex items-center gap-2 text-muted-foreground">
						<span class="font-medium">Target:</span>
						<span>Series A-B fintech & healthtech startups</span>
					</div>
					<div class="flex items-center gap-2 text-muted-foreground">
						<span class="font-medium">Focus:</span>
						<span>Zero-downtime refactoring</span>
					</div>
				</div>
			</div>

			<!-- Navigation sections -->
			<div class="grid grid-cols-2 gap-8 lg:col-span-2 lg:grid-cols-2">
				{#each navigation
					.filter((item) => item.showInFooter !== false)
					.sort((a, b) => (b?.children?.length || 0) - (a?.children?.length || 0)) as section}
					<div class="text-muted-foreground">
						<h3 class="text-foreground font-medium text-sm mb-4" class:hidden={!section?.children}>
							{section.label}
						</h3>
						{#if section.children}
							<ul class="flex flex-col gap-3">
								{#each section.children.filter((child) => child.showInFooter !== false) as item}
									<li>
										<a 
											href={item.href} 
											class="text-sm hover:text-foreground transition-colors duration-200" 
											target={item?.target || undefined}
										>
											{item.label}
										</a>
									</li>
								{/each}
							</ul>
						{:else}
							<a 
								href={section.href} 
								class="text-sm hover:text-foreground transition-colors duration-200" 
								target={section?.target || undefined}
							>
								{section.label}
							</a>
						{/if}
					</div>
				{/each}
			</div>
		</div>

		<!-- Contact and additional info -->
		<div class="mt-12 pt-8 border-t" style="border-color: var(--color-border);">
			<div class="grid gap-8 lg:grid-cols-3">
				<div>
					<h4 class="font-medium text-sm mb-3">Get started</h4>
					<p class="text-muted-foreground text-sm mb-4">
						Ready to transform your codebase without disrupting your business?
					</p>
					<a 
						href="/contact" 
						class="inline-flex items-center text-sm font-medium hover:text-foreground transition-colors duration-200"
					>
						Schedule a consultation
						<svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
						</svg>
					</a>
				</div>
				
				<div>
					<h4 class="font-medium text-sm mb-3">Industries</h4>
					<ul class="text-muted-foreground text-sm space-y-2">
						<li>Fintech startups</li>
						<li>Healthtech companies</li>
						<li>Series A-C ventures</li>
					</ul>
				</div>

				<div>
					<h4 class="font-medium text-sm mb-3">Approach</h4>
					<ul class="text-muted-foreground text-sm space-y-2">
						<li>Incremental refactoring</li>
						<li>Zero-downtime migrations</li>
						<li>Compliance-ready systems</li>
					</ul>
				</div>
			</div>
		</div>

		<!-- Footer bottom section -->
		<div
			class="mt-12 pt-6 border-t"
			style="border-color: var(--color-border); color: var(--color-muted-foreground);"
		>
			<div class="flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-between">
				<div class="text-sm">
					&copy; {CONFIG.companyName} {new Date().getFullYear()}. All rights reserved.
				</div>
				<div class="flex items-center gap-6">
					<a href="/privacy" class="text-sm hover:text-foreground transition-colors duration-200">
						Privacy Policy
					</a>
					<a href="/terms" class="text-sm hover:text-foreground transition-colors duration-200">
						Terms of Service
					</a>
					<div class="hidden lg:block"><Signature /></div>
				</div>
			</div>
		</div>
	</div>
</footer>

<style lang="postcss">
	@reference '../../../app.css';

	footer {
		background: var(--color-background);
		border-top: 1px solid var(--color-border);
	}

	a {
		@apply inline-block transition-all duration-200 ease-out;
		color: var(--color-muted-foreground);
		text-decoration: none;

		&:hover {
			color: var(--color-foreground);
		}
	}

	h4 {
		color: var(--color-foreground);
	}

	.text-headline {
		color: var(--color-foreground);
		font-weight: 600;
	}
</style>
