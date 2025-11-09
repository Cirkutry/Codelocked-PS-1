<script lang="ts">
  import Autoplay from "embla-carousel-autoplay";
  import { Card, CardHeader, CardTitle, CardContent } from "$lib/components/ui/card";
  import { buttonVariants } from "$lib/components/ui/button";
  import * as Dialog from "$lib/components/ui/dialog";
  import * as Carousel from "$lib/components/ui/carousel";
  import { Image, FileDown } from '@lucide/svelte';
  import i1 from "$lib/assets/images/i1.jpg";
  import i2 from "$lib/assets/images/i2.webp";
  import i3 from "$lib/assets/videos/i3.jpg";

  const plugin = Autoplay({ delay: 1500, stopOnInteraction: false, stopOnMouseEnter: true });

  const media = [
    { src: i1, type: "image", alt: "Interior 1" },
    { src: i2, type: "image", alt: "Interior 2" },
    { src: i3, type: "image", alt: "Interior 3" }
  ];
</script>

<section id="archive" class="container mx-auto px-6">
  <div class="max-w-7xl mx-auto flex flex-col items-center py-12 gap-8">
    <div class="w-full text-center lg:text-left">
      <h2 class="text-4xl font-extrabold mb-8">Archive</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <Dialog.Root>
          <Card>
            <CardHeader class="text-lg text-primary">
              <Image class="w-8 h-8 text-primary" />
              <CardTitle class="text-lg text-primary">Photos</CardTitle>
            </CardHeader>
            <CardContent class="text-muted-foreground">
              <p class="mb-4">
                Browse through snapshots of the interiors of the base.
              </p>
              <Dialog.Trigger class={buttonVariants({ variant: "outline" })}>
                View Gallery
              </Dialog.Trigger>
            </CardContent>
            <Dialog.Content
              class="max-h-[90vh] w-[90vw]"
            >
              <Dialog.Header class="text-lg text-primary">
                <Dialog.Title>Photos</Dialog.Title>
                <Dialog.Description>Browse through snapshots of the interiors of the base.</Dialog.Description>
              </Dialog.Header>
              
              <div class="relative w-full">
                <Carousel.Root
                  opts={{ loop: true }}
                  plugins={[plugin]}
                  class="w-full"
                >
                  <Carousel.Content>
                    {#each media as item, i (i)}
                      <Carousel.Item class="basis-full p-2">
                        <div class="w-full flex items-center justify-center">
                          {#if item.type === "image"}
                            <img
                              src={item.src}
                              alt={item.alt}
                            />
                          {:else}
                            <video
                              src={item.src}
                              controls
                              autoplay
                              muted
                              loop
                              class={`rounded-lg object-contain ${item.alt === "3D Model" ? 'max-h-[45vh] w-auto' : 'max-h-[65vh] w-auto'}`}
                            >
                            </video>
                          {/if}
                        </div>
                      </Carousel.Item>
                    {/each}
                  </Carousel.Content>
                  <Carousel.Previous class="hidden md:flex"/>
                  <Carousel.Next class="hidden md:flex"/>
                </Carousel.Root>
              </div>
            </Dialog.Content>
          </Card>
        </Dialog.Root>

        <Card>
          <CardHeader class="text-lg text-primary">
            <FileDown class="w-8 h-8 text-primary" />
            <CardTitle class="text-lg text-primary">Mission brief</CardTitle>
          </CardHeader>
          <CardContent class="text-muted-foreground">
            <p class="mb-4">
              Download the official Olympus Mons Habitat Exploring Mission Brief PDF.
            </p>
            <a
              href="src/lib/assets/Olympus Mons Habitat Exploring Mission Brief.pdf"
              download
              class={buttonVariants({ variant: "outline" })}
            >
              Download PDF
            </a>
          </CardContent>
        </Card>
      </div>
    </div>
  </div>
</section>