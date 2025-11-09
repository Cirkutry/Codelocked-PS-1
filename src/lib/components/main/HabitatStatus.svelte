<script lang="ts">
	import { Card, CardContent, CardHeader, CardTitle } from "$lib/components/ui/card";
	import { Button } from "$lib/components/ui/button";
	import { onMount } from "svelte";

	let oxygen = 87;
	let power = 64;
	let waterRecycle = 92;
	let emergency = false;
	let interval: number;
	let emergencyTimeout: number;

	function toggleEmergency() {
		if (emergency) {
			emergency = false;
			clearTimeout(emergencyTimeout);
		} else {
			emergency = true;
			clearTimeout(emergencyTimeout);
			emergencyTimeout = setTimeout(() => (emergency = false), 5000);
		}
	}

	onMount(() => {
		interval = setInterval(() => {
			oxygen = Math.max(40, Math.min(100, oxygen + (Math.random() - 0.5) * 2));
			power = Math.max(10, Math.min(100, power + (Math.random() - 0.5) * 1.5));
			waterRecycle = Math.max(50, Math.min(100, waterRecycle + (Math.random() - 0.5) * 1));
		}, 3500);

		return () => {
			clearInterval(interval);
			clearTimeout(emergencyTimeout);
		};
	});
</script>

<section id="habitat-status" class="container mx-auto px-6">
	<div class="max-w-7xl mx-auto flex flex-col items-center py-12 gap-8 w-full">
		<div class="w-full text-center lg:text-left">
			<h2 class="text-4xl font-extrabold mb-8">Habitat Status</h2>

			<div class="relative w-full mx-auto">
				{#if emergency}
					<div class="absolute inset-0 bg-red-700/95 flex items-center justify-center z-30 rounded-lg transition-opacity duration-500">
						<div class="text-5xl font-extrabold tracking-widest text-white uppercase drop-shadow-lg">
							EMERGENCY
						</div>
					</div>
				{/if}

				<Card class="w-full relative">
					<CardHeader>
						<CardTitle>Olympus Mons Base - Habitat Status</CardTitle>
					</CardHeader>

					<CardContent class="flex flex-col gap-4 relative">

						<div class="flex items-center gap-4">
							<div class="flex-shrink-0 w-20">
								<div class="text-sm text-muted-foreground">Oxygen</div>
								<div class="text-2xl font-semibold">{Math.round(oxygen)}%</div>
							</div>
							<div class="flex-1 h-4 bg-card rounded-md overflow-hidden">
								<div
									class={`h-4 bg-gradient-to-r ${
										oxygen > 60
											? "from-emerald-400 to-emerald-600"
											: oxygen > 30
											? "from-amber-400 to-amber-600"
											: "from-red-500 to-red-700"
									}`}
									style={`width: ${oxygen}%`}
								></div>
							</div>
						</div>

						<div class="flex items-center gap-4">
							<div class="flex-shrink-0 w-20">
								<div class="text-sm text-muted-foreground">Power</div>
								<div class="text-2xl font-semibold">{Math.round(power)}%</div>
							</div>
							<div class="flex-1 h-4 bg-card rounded-md overflow-hidden">
								<div
									class={`h-4 bg-gradient-to-r ${
										power > 60
											? "from-sky-400 to-sky-600"
											: power > 30
											? "from-orange-400 to-orange-600"
											: "from-red-500 to-red-700"
									}`}
									style={`width: ${power}%`}
								></div>
							</div>
						</div>

						<div class="flex items-center gap-4">
							<div class="flex-shrink-0 w-20">
								<div class="text-sm text-muted-foreground">Water Recycling</div>
								<div class="text-2xl font-semibold">{Math.round(waterRecycle)}%</div>
							</div>
							<div class="flex-1 h-4 bg-card rounded-full overflow-hidden">
								<div class="h-4 bg-teal-500" style={`width: ${waterRecycle}%`}></div>
							</div>
						</div>

						<div class="flex items-center gap-3 mt-6 relative z-40">
							<div
								role="button"
								tabindex="0"
								class="inline-block"
								on:click={toggleEmergency}
								on:keydown={(e) =>
									(e.key === "Enter" || e.key === " ") &&
									(e.preventDefault(), toggleEmergency())
								}
							>
								<Button variant="destructive" size="lg" aria-pressed={emergency}>
									{emergency ? "Release Manual Override" : "Manual Override"}
								</Button>
							</div>
							<p class="text-sm text-muted-foreground">
								Toggles critical alert state for demonstration.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</div>
	</div>
</section>