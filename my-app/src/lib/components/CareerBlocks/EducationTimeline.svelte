<script lang="ts">
	import { onMount } from 'svelte';
    import { Button } from "$lib/components/ui/button";
    export var showCareer = false;

    onMount(()=>{
        var svgs = document.getElementsByTagName("svg");
        var educationButton = document.getElementById("educationButton");

        if(educationButton) educationButton.style.marginLeft = ((window.innerWidth/2)-100) + "px";
        Array.prototype.forEach.call(svgs, function(svg) {
            if(svg) svg.style.marginLeft = ((innerWidth/2)) + "px";
        });


    })

 </script>

<svg width="200" height="10%"><line x1="0" y1="0" x2="0" y2="100%" stroke="white" stroke-dasharray="10,10" /></svg>
    <Button id="educationButton" class="w-[200px] mt-0" variant="outline" href="/Career">Go to my education?</Button>
<svg width="200" height="100"><line x1="0" y1="0" x2="0" y2="100%" stroke="white"/></svg>

<slot></slot>

<svg width="200" height="100"><line x1="0" y1="0" x2="0" y2="100%" stroke="white"/></svg>
<svg width="200" height="100"><line x1="0" y1="0" x2="0" y2="100%" stroke="white" stroke-dasharray="10,10" /></svg>