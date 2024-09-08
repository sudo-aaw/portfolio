<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";
    export let points = [
        ];
    export var className = "w-[350px] mx-auto"
</script>

<Card.Root class={className}>
    <Card.Content>
        <ul  class="my-6 ml-6 list-disc [&>li]:mt-2">
            {#each points as point}
                <li>{point}</li>
            {/each}
        </ul>
    </Card.Content>
</Card.Root>