<script lang="ts">
  import Autoplay from "embla-carousel-autoplay";
  import * as Card from "$lib/components/ui/card/index.js";
  import * as Carousel from "$lib/components/ui/carousel/index.js";
  import e1 from "$lib/assets/images/e1.jpg";
  import e2 from "$lib/assets/images/e2.webp";
  import e3 from "$lib/assets/images/e3.jpg";

  const plugin = Autoplay({ delay: 1500, stopOnInteraction: false, stopOnMouseEnter: true });

  const slides = [
    { src: e1, title: "Mars Habitat 1" },
    { src: e2, title: "Mars Habitat 2" },
    { src: e3, title: "Mars Habitat 3" },
  ];
</script>

<section id="environment" class="container mx-auto pb-8 px-6">
  <div class="max-w-7xl mx-auto flex flex-col pt-12 gap-8 w-full">
    <h2 class="text-4xl font-extrabold mb-4">Environment</h2>
    <p class="text-lg text-muted-foreground mb-6">
      Live shots of environmental conditions at Olympus Mons Base, streamed directly from our Mars habitat. Stay connected with the crew's surroundings as they explore and conduct research on the Red Planet.
    </p>

    <Carousel.Root opts={{ loop: true }} plugins={[plugin]} class="w-full w-full">
      <Carousel.Content>
        {#each slides as slide, i (i)}
          <Carousel.Item class="basis-full sm:basis-4/5 lg:basis-3/4 p-4">
            <Card.Root class="overflow-hidden rounded-xl w-full h-[400px] sm:h-[450px] lg:h-[500px]">
              <Card.Content class="p-0 w-full h-full">
                <img
                  src={slide.src}
                  alt={slide.title}
                  class="w-full h-full rounded-xl object-cover"
                />
              </Card.Content>
            </Card.Root>
          </Carousel.Item>
        {/each}
      </Carousel.Content>

      <div class="flex justify-center gap-4 mt-6">
        <Carousel.Previous class="static w-10 h-10 sm:w-12 sm:h-12" />
        <Carousel.Next class="static w-10 h-10 sm:w-12 sm:h-12" />
      </div>
    </Carousel.Root>
  </div>
</section>
