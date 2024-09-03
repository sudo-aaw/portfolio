<script lang="ts">
	import ProfilePage from '$lib/components/ProfilePage.svelte';
	import { onMount } from 'svelte';
    import TileGrid from './../lib/components/pathFinding/TileGrid.svelte';
	import { browser } from '$app/environment';

    var tileSize = 40;
    var innerWidth = 0;
    var innerHeight = 0;
    let navbarHeight = 0;
    // let profileClass = "absolute top-["+ (11*tileSize+navbarHeight)+"px] left-[120px]"

    let profileClass = "absolute top-[52px] left-[120px]"

    onMount(()=>{
        const navbar = document.getElementById("navbar");
        navbarHeight = navbar ? navbar?.clientHeight : 0;
        if(navbar){
            navbarHeight=navbar.clientHeight;
            navbarHeight += parseInt(window.getComputedStyle(navbar).getPropertyValue('border-top'));
            navbarHeight += parseInt(window.getComputedStyle(navbar).getPropertyValue('border-bottom'));
        }        
    })
    $:xTiles = Math.floor(innerWidth/tileSize);
    $: (() => {
        // input is not actually used but present as a statement
        (innerHeight);
        var topOffset=navbarHeight+8*tileSize;(navbarHeight+11*tileSize)
        var leftOffset = (xTiles/2-5)*tileSize;
        if(browser && document.getElementById("profileCard")){
            document.getElementById("profileCard").style.top=topOffset+"px"
            document.getElementById("profileCard").style.left=leftOffset+"px"
        }
    }) ()
</script>

<svelte:window bind:innerWidth bind:innerHeight />
<TileGrid bind:xTiles/>
<!-- <TileGrid bind:xTiles></TileGrid> -->
<div class={profileClass} id="profileCard">
    <ProfilePage />  
</div>
   
