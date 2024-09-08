<script lang="ts">
    import * as Card from '$lib/components/ui/card/index.js';
	import { onMount } from 'svelte';

    export var educationLevel = ""
    export var schoolName = ""
    export var dates = ""
	export var points : string[] = [];
    export var morePoints : string[] = [];
    var show = false;


    var message = "Click for more details"

    function handleChangeDetail(){
        console.log("change")
        message = message === "Click for more details" ? "Click for less details" : "Click for more details";
        show = !show;
    }


    onMount(()=>{
        var summary = document.getElementById(educationLevel+"summary");
        var svg = document.getElementById(educationLevel+"svg");
        innerWidth=window.innerWidth;
        if(summary) summary.style.marginLeft = ((innerWidth/2) - 175) + "px ";
        if(svg) svg.style.marginLeft = ((innerWidth/2)) + "px ";
    })


</script>

    <div class="flex flex-row justify-right mt-0">
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <div on:click={handleChangeDetail}>
            <Card.Root id={educationLevel+"summary"} class="w-[350px]">
                <Card.Header>
                    <Card.Title class="text-center">{educationLevel}</Card.Title>
                    <Card.Title class="text-center">{schoolName}</Card.Title>
                    <Card.Description class="text-center">{dates}</Card.Description>
                </Card.Header>
                
                <Card.Content>
                    <ul  class="my-6 ml-6 list-disc [&>li]:mt-2">
                        {#each points as point}
                            <li>{point}</li>
                        {/each}
                    </ul>
                </Card.Content>
                <p class="text-center self-center">{message}</p>
            </Card.Root>
          
        </div>
        

        {#if show}
            <Card.Root class="mx-0 w-[500px]">
                <Card.Content>
                    <div class="flex flex-row">
                        <ul  class="my-6 ml-6 list-disc [&>li]:mt-2">
                            {#each morePoints as point,index}
                                {#if index<6}
                                    <li>{point}</li>
                                {/if}
                            {/each}
                        </ul>
                        <ul  class="my-6 ml-12 list-disc [&>li]:mt-2">
                            {#each morePoints as point,index}
                            {#if index>=6}
                                <li>{point}</li>
                            {/if}
                            {/each}
                        </ul>
                    
  
                </Card.Content>
            </Card.Root>
        {/if}
      
    </div>
    <svg id={educationLevel+"svg"} width="200" height="100"><line x1="0" y1="0" x2="0" y2="100%" stroke="white" /></svg>



