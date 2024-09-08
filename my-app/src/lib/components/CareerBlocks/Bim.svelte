<script lang="ts">
    import * as Card from "$lib/components/ui/card/index.js";

	import HTML from '$lib/components/techIcons/Adobe.svelte';
	import Css from '$lib/components/techIcons/CSS.svelte';
	import Js from '$lib/components/techIcons/JS.svelte';
	import Python from '$lib/components/techIcons/Python.svelte';
	import Flask from '$lib/components/techIcons/Flask.svelte';
	import MySql from '$lib/components/techIcons/MySql.svelte';
</script>

<Card.Root class="w-[350px] mx-auto">
    <Card.Header>
      <Card.Title class="text-center">Engineering Assistant</Card.Title>
      <Card.Title class="text-center">@BIM UK Ltd</Card.Title>
      <Card.Description class="text-center">June 2021 - October 2021</Card.Description>
    </Card.Header>
    <Card.Content>
        <div class = "w-1/1 h-[40px] flex flex-row justify-evenly align-center">
            <Python/>
            <Flask/>
            <MySql/>
            <Css/>
            <HTML/>
            <Js/>
        </div>
    </Card.Content>
  </Card.Root>