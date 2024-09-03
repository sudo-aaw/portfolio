	
<script lang="ts">
  import Autoplay from "embla-carousel-autoplay";
  import * as Card from "$lib/components/ui/card/index.js";
  import * as Carousel from "$lib/components/ui/carousel/index.js";
 
  const plugin = Autoplay({ delay: 2000, stopOnInteraction: true });

    const projects = ["backend","dashboard","projectPouch"]



</script>

<div class="w-4/5 mx-auto mt-2 flex justify-center">
    <Carousel.Root
    plugins={[plugin]}
    class="w-full max-w-xs"
    on:mousenter={plugin.stop}
    on:mouseleave={plugin.reset}
  >
    <Carousel.Content>
      {#each projects as _, i (i)}
        <Carousel.Item>
          <div class="p-1">
            <Card.Root>
              <Card.Content
                class="flex aspect-square items-center justify-center p-6"
              >
                <span class="text-4xl font-semibold">{i + 1}. {_}</span>
              </Card.Content>
            </Card.Root>
          </div>
        </Carousel.Item>
      {/each}
    </Carousel.Content>
    <Carousel.Previous />
    <Carousel.Next />
  </Carousel.Root>

</div>


  
  