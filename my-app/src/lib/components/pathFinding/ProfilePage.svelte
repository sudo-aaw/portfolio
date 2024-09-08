	
<script lang="ts">
    import { Button } from "$lib/components/ui/button/index.js";
    import * as Card from "$lib/components/ui/card/index.js";
    import SocialIcons from '@rodneylab/svelte-social-icons';



  
    export let tileSize = 40;
    let tileClass = "w-["+tileSize*10+"px] mx-auto"
    let navbarHeight = 0;


    let innerWidth = 0
    let innerHeight = 0
  </script>
  
   <svelte:window bind:innerWidth bind:innerHeight />
   <div class="flex flex-col w-[320px]">
    <Card.Root class={tileClass}>
        <Card.Header>
          <Card.Title class="text-center">Archie Aiken-Wood</Card.Title>
          <Card.Description class="text-center">Software Engineer || Business Intelligence</Card.Description>
        </Card.Header>
        <Card.Content>
          <form>
            <div class="grid w-full items-center gap-4">
              <div class="flex justify-center gap-4">
                <SocialIcons alt="" network="github" fgColor="#eeeeee" bgColor="#111111" />
                <SocialIcons alt="" network="linkedin" fgColor="#eeeeee" bgColor="#111111" />
                <SocialIcons alt="" network="email" fgColor="#eeeeee" bgColor="#111111" />
              </div>
            </div>
          </form>
        </Card.Content>
        <Card.Title class="text-center my-2"></Card.Title>

        <Card.Footer class="flex justify-between">
          <Button>Shuffle Tiles</Button>
          <Button>How to use demo?</Button>
        </Card.Footer>
      </Card.Root>
   </div>
