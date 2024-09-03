	
<script lang="ts">
    import { Button } from "$lib/components/ui/button/index.js";
    import * as Card from "$lib/components/ui/card/index.js";
    import * as Select from "$lib/components/ui/select/index.js";
    import { Input } from "$lib/components/ui/input/index.js";
    import { Label } from "$lib/components/ui/label/index.js";
    import SocialIcons from '@rodneylab/svelte-social-icons';
	import { onMount } from "svelte";


  
    export let tileSize = 40;
    let tileClass = "w-["+tileSize*10+"px] mx-auto"
    let navbarHeight = 0;


    let innerWidth = 0
    let innerHeight = 0
  </script>
  
   <svelte:window bind:innerWidth bind:innerHeight />
   <div class="flex flex-col min-h-screen mt-10">
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
          <Button variant="outline">Cancel</Button>
          <Button>Deploy</Button>
        </Card.Footer>
      </Card.Root>
   </div>
