<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";
    export let points = [
        ];

</script>

<Card.Root class="w-[350px] mx-auto">
    <Card.Content>
        <ul  class="my-6 ml-6 list-disc [&>li]:mt-2">
        {#each points as point}
            <li>{point}</li>
        {/each}
    </ul>
<!--            
            <li>Simplified the ordering of new assets by automating the approval and movement of the order sheet document </li>
            <li>x </li>
            <li></li> -->
    
    </Card.Content>
  </Card.Root>