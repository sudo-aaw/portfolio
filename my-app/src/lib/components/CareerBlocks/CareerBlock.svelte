<script lang="ts">
	import PowerBI from './../techIcons/PowerBI.svelte';
	import HTML from '$lib/components/techIcons/HTML.svelte';
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
	import BulletPointBlock from '$lib/components/CareerBlocks/BulletPointBlock.svelte';
	import Mexico from '../techIcons/Mexico.svelte';

	export var show: boolean = false;
	export var hover: boolean = false;
	export var duration = 1000;

	export var jobTitle = '';
	export var companyName = '';
	export var dates = '';
	export var placement = '';

	export var points = [];
	export var techStack = ['Python', 'Flask', 'MySql', 'Css', 'HTML', 'Js'];

	function stringToComponent(tech: string) {
		let component;
		switch (tech) {
			case 'Python':
				component = Python;
				break;
			case 'MySql':
				component = MySql;
				break;
			case 'Css':
				component = Css;
				break;
			case 'Js':
				component = Js;
				break;
			case 'Adobe':
				component = Adobe;
				break;
			case 'Excel':
				component = Excel;
				break;
			case 'Flask':
				component = Flask;
				break;
			case 'Github':
				component = Github;
				break;
			case 'HTML':
				component = HTML;
				break;
			case 'Node':
				component = Node;
				break;
			case 'Postgre':
				component = Postgre;
				break;
			case 'PowerBI':
				component = PowerBi;
				break;
			case 'PowerShell':
				component = PowerShell;
				break;
			case 'Quicksight':
				component = Quicksight;
				break;
			case 'React':
				component = React;
				break;
                case 'Mexico':
				component = Mexico;
				break;
			default:
				break;
		}
		return component;
	}
</script>


<svg width="200" height="500"><line x1="0" y1="250" x2="100%" y2="250" stroke="white" /></svg>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-mouse-events-have-key-events -->
<div
	class="mt-10 flex flex-col"
	on:mouseenter={() => {
		hover = true;
		show = true;
	}}
	on:mouseleave={() => {
		hover = false;
		show = false;
	}}
>
	{#if show}
		<div class="opacity-0" transition:fade={{ delay: 250, duration: duration }}>
			<BulletPointBlock {points}/>
		</div>
	{/if}

	<Card.Root class="mx-auto w-[350px]">
		<Card.Header>
			<Card.Title class="text-center">{jobTitle}</Card.Title>
			<Card.Title class="text-center">{companyName}</Card.Title>
			<Card.Description class="text-center">{dates}</Card.Description>
			{#if placement !== ''}
				<Card.Description class="text-center">{placement}</Card.Description>
			{/if}
		</Card.Header>
		<Card.Content>
			<div class="w-1/1 align-center flex h-[40px] flex-row justify-evenly">
				{#each techStack as tech}
					<svelte:component this={stringToComponent(tech)} />
				{/each}
			</div>
		</Card.Content>
	</Card.Root>

	{#if show}
		<div transition:fade={{ delay: 250, duration: duration }}>
			<BulletPointBlock {points}/>
		</div>
	{/if}
</div>
