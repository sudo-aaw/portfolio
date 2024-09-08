<script lang="ts">
	import HTML from '../../lib/components/techIcons/HTML.svelte';
	import React from '$lib/components/techIcons/React.svelte';
	import * as Card from '$lib/components/ui/card/index.js';
	import Github from '$lib/components/techIcons/Github.svelte';
	import Node from '$lib/components/techIcons/Node.svelte';
	import Adobe from '$lib/components/techIcons/Adobe.svelte';
	import Css from '$lib/components/techIcons/CSS.svelte';
	import Js from '$lib/components/techIcons/JS.svelte';
	import PowerShell from '$lib/components/techIcons/PowerShell.svelte';
	import PowerBi from '$lib/components/techIcons/PowerBI.svelte';
	import Postgre from '$lib/components/techIcons/Postgre.svelte';
	import Quicksight from '$lib/components/techIcons/Quicksight.svelte';
	import Excel from '$lib/components/techIcons/Excel.svelte';
	import Python from '$lib/components/techIcons/Python.svelte';
	import Flask from '$lib/components/techIcons/Flask.svelte';
	import MySql from '$lib/components/techIcons/MySql.svelte';

	import { fade } from 'svelte/transition';
	import Bim from '$lib/components/CareerBlocks/Bim.svelte';
	import CareerBlock from '$lib/components/CareerBlocks/CareerBlock.svelte';
	import CareerTimeline from '$lib/components/CareerBlocks/CareerTimeline.svelte';

	var showBim = true;
	var showAmazon = false;
	var showTravelling = false;
	var showLloydsPlacement1 = false;
	var showLloydsPlacement2 = false;

	var hoverBim = false;
	var hoverAmazon = false;
	var hoverTravelling = false;
	var hoverLloydsPlacement1 = false;
	var hoverLloydsPlacement2 = false;

	var duration = 1000;

	setInterval(showNext, 2000);

	var position = 1;
	async function showNext() {
		showBim = false || hoverBim;
		showAmazon = false || hoverAmazon;
		showTravelling = false || hoverTravelling;
		showLloydsPlacement1 = false || hoverLloydsPlacement1;
		showLloydsPlacement2 = false || hoverLloydsPlacement2;
		switch (position) {
			case 1:
				showBim = true;
				break;
			case 2:
				showAmazon = true;
				break;
			case 3:
				showTravelling = true;
				break;
			case 4:
				showLloydsPlacement1 = true;
				break;
			case 5:
				showLloydsPlacement2 = true;
				position = 0;
				break;
			default:
				break;
		}
		position++;
	}
</script>

<div id="page" class="align-center flex h-screen flex-row items-center">
	<CareerTimeline>
		<CareerBlock
			{duration}
			show={showBim}
			bind:hover={hoverBim}
			jobTitle="Engineering Assistant"
			companyName="@BIM UK Ltd"
			dates="June 2021 - October 2021"
			techStack={['Python', 'Flask', 'MySql', 'Css', 'HTML', 'Js']}
		>
			<span slot="detail"> <Bim /> </span>
		</CareerBlock>

		<CareerBlock
			{duration}
			show={showAmazon}
			bind:hover={hoverAmazon}
			jobTitle="Business Intelligence Intern"
			companyName="@Amazon"
			dates="June 2022 - December 2022"
			techStack={['Postgre', 'Quicksight', 'Excel']}
		>
			<span slot="detail"> <Bim /> </span>
		</CareerBlock>

		<CareerBlock
			{duration}
			show={showTravelling}
			bind:hover={hoverTravelling}
			jobTitle="Travelling"
			companyName="@Mexico"
			dates="January 2023 - June 2024"
			techStack={['Mexico']}
		>
			<span slot="detail"> <Bim /> </span>
		</CareerBlock>

		<CareerBlock
			{duration}
			show={showLloydsPlacement1}
			bind:hover={hoverLloydsPlacement1}
			jobTitle="Graduate Technology Engineer"
			companyName="@Lloyds Banking Group"
			placement="Placement 1 - Business Intelligence"
			dates="September 2023 - May-2024"
			techStack={['PowerShell', 'Github', 'PowerBI']}
		>
			<span slot="detail"> <Bim /> </span>
		</CareerBlock>

		<CareerBlock
			{duration}
			show={showLloydsPlacement2}
			bind:hover={hoverLloydsPlacement2}
			jobTitle="Graduate Technology Engineer"
			companyName="@Lloyds Banking Group"
			placement="Placement 2 - Frontend engineer"
			dates="May 2024 - Current"
			techStack={['React', 'Css', 'HTML', 'Github', 'Adobe', 'Node', 'Js']}
		>
			<span slot="detail"> <Bim /> </span>
		</CareerBlock>
	</CareerTimeline>
</div>

<style>
	#page {
		background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
		background-size: 400% 400%;
		animation: gradient 15s ease infinite;
		height: 100vh;
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
</style>
