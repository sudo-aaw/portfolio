	
<script lang="ts">
    import { Button } from "$lib/components/ui/button/index.js";
    import * as Card from "$lib/components/ui/card/index.js";


    export let tileSize = 40;
    let tileClass = "w-["+tileSize*10+"px] mx-auto"

    let innerWidth = 0
    let innerHeight = 0

    export var title = ""
    export var description = "";
    export var buttonText = ""
    export var href = ""
  </script>
  
   <svelte:window bind:innerWidth bind:innerHeight />
   <div class="flex flex-col w-[320px]">
    <Card.Root class={tileClass}>
        <Card.Header>
          <Card.Title class="text-center">{title}</Card.Title>
          <Card.Description class="text-center">{description}</Card.Description>
        </Card.Header>
        <Card.Content>
            <div class="flex justify-center">
                <Button {href} >{buttonText}</Button>
            </div>
            
        </Card.Content>
      </Card.Root>
   </div>
