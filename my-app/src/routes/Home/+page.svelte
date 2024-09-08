<script lang="ts">
	import ProfilePage from '$lib/components/pathFinding/ProfilePage.svelte';
	import { onMount } from 'svelte';
    import TileGrid from '$lib/components/pathFinding/TileGrid.svelte';
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
        (innerHeight);
        var topOffset=navbarHeight+8*tileSize;(navbarHeight+11*tileSize)
        var leftOffset = (xTiles/2-5)*tileSize;
        if(browser){
            var profileCard = document.getElementById("profileCard")
            if(profileCard){
                profileCard.style.top=topOffset+"80px"
                profileCard.style.left=leftOffset+"0px"
            }
        }
    }) ()


</script>

<svelte:window bind:innerWidth bind:innerHeight />

<TileGrid bind:xTiles/>
<!-- <ProfilePage />   -->
<!-- <TileGrid bind:xTiles></TileGrid> -->
   
