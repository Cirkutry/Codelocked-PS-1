<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import habitatPreview from "$lib/assets/images/Olympus_Mons_caldera.jpg";
</script>

<section id="hero" class="container mx-auto pb-8 px-6">
  <div class="max-w-7xl mx-auto grid lg:grid-cols-2 py-12">
    <div>
      <h1 class="text-5xl font-extrabold mb-4">Olympus Mons Base Dashboard</h1>
      <p class="text-lg text-muted-foreground mb-6">
        Welcome to the central operations console for the <span class="font-semibold">Olympus Mons Research Habitat</span> -
        humanity’s newest outpost on Mars. This dashboard provides real-time
        environmental statistics including oxygen levels, remaining power, and water
        recycling efficiency, ensuring stable conditions for the crew.
      </p>

      <p class="text-lg text-muted-foreground mb-6">
        Below, you’ll also find the crew’s operational log - a running record of daily
        mission updates, maintenance reports, and on-site discoveries.
      </p>

      <div class="flex flex-col sm:flex-row sm:justify-start gap-3 mb-8 sm:mb-0">
        <Button variant="default" size="lg" href="#habitat-status">View Habitat Status</Button>
        <Button variant="outline" size="lg" href="#log">Open Crew Log</Button>
      </div>
    </div>

    <div class="flex justify-center lg:justify-end">
      <img
        src={habitatPreview}
        alt="Olympus Mons Habitat Dashboard preview"
        class="max-w-full w-96 sm:w-[28rem] rounded-xl shadow-xl"
      />
    </div>
  </div>

  <div class="mt-12 max-w-4xl mx-auto px-4">
    <slot name="video">
      <div class="bg-muted/20 rounded-lg p-6 text-center text-sm text-muted-foreground">
        Mission briefing video coming soon.
      </div>
    </slot>
  </div>
</section>
