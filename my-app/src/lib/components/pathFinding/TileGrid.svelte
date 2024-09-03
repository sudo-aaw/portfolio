<script lang="ts">
	import { onMount } from "svelte";

    const tileSize = 40;
    let anchorTile = [0,0];
    let activeNumber = [0,0];

    let innerWidth = 0
    let innerHeight = 0
    var navbarHeight = 0;

    const archieTilesPattern = [[1,4],[1,3], [1,2], [1,1], [1,0], [2,0], [3,0], [3,1], [3,2], [3,3],[3,4],[2,2], [5,4], [5,3], [5,2], [5,1], [5,0], [6,0], [7,1], [6,2], [7,3], [7,4],[10,0], [9,0], [9,1], [9,2], [9,3], [9,4], [10,4], [11,4], [11,0], [13,4], [13,3], [13,2], [13,1], [13,0], [14,2], [15,0], [15,1], [15,2], [15,3],[15,4],[17,4], [18,4], [19,4], [18,3], [18,2], [18,1], [17,0], [18,0], [19,0],[21,4], [22,4], [21,3], [21,2], [22,2], [21,0], [22,0], [21,1], [23,4], [23,2],[23,0]];

    $: archieTiles = new Set();
    let archieXTiles = 25;
    let archieYTiles = 7;

    export let xTiles = Math.floor(innerWidth/tileSize);

    $:yTiles = Math.floor((innerHeight-navbarHeight)/tileSize);

    $:archieStartX = (xTiles/2)-(archieXTiles/2);
    $:archieStartY = (yTiles/2)-(archieYTiles/2);

    $:containerWidth = xTiles*tileSize;
    $:containerHeight = yTiles*tileSize;
    $:containerClass = "flex flex-row flex-wrap mx-auto w-["+containerWidth+"px]"+" h-["+containerHeight+"px]"; 
    
    function setClassActive(x:number,y:number){
        activeNumber = [x,y];
        resetTileClasses();        
    }

    function setAnchorTile(x:number,y:number){
        anchorTile= [x,y];
        resetTileClasses();
    }

    function resetTileClasses(){
        let newSet = new Set();
        console.log(archieStartY)
        archieTilesPattern.forEach(tile => {
            let x = Math.floor(tile[0]+archieStartX);
            let y = Math.floor(tile[1]+archieStartY);
            let coord = x+","+y;
            // console.log(coord)
            newSet.add(coord);
        });
        archieTiles=newSet;

        for(let x = 0; x< xTiles; x++){
            for(let y = 0; y< yTiles; y++){
                var tileID = x+","+y
                const tile = document.getElementById(tileID);
                while(!tile){}
                if(tile) tile.className=getTileClass([x,y]);
            }
        }
    }
        
    function getTileClass(coord){
        if(coordsAreEqual(coord,activeNumber)) return "bg-black w-["+tileSize+"px] h-["+tileSize+"px] border-2"
        if(coordsAreEqual(coord,anchorTile)) return "bg-slate-500 w-["+tileSize+"px] h-["+tileSize+"px] border-2"
        if(isAWallTile(coord)) return "bg-black w-["+tileSize+"px] h-["+tileSize+"px] border-2"
        return "bg-slate-50 w-["+tileSize+"px] h-["+tileSize+"px] border-2"
    }

    function coordsAreEqual(coordA,coordB){
        return (coordA[0]===coordB[0] &&coordA[1]===coordB[1])
    }

    function isAWallTile(coord){
        var coordAsString = coord[0] + "," + coord[1];
        return archieTiles.has(coordAsString);
    }

    onMount(()=>{
        const navbar = document.getElementById("navbar");
        navbarHeight = navbar ? navbar?.clientHeight : 0;
        resetTileClasses();
    })


    

</script>

<svelte:window bind:innerWidth bind:innerHeight />

<div class={containerClass}>
    {#each Array(yTiles) as _, y}
        {#each Array(xTiles) as _, x} 
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore a11y-no-static-element-interactions -->
            <div id={x+","+y}
                class="w-[40px] h-[40px]"
                on:mouseenter={()=>setClassActive(x,y)}
                on:click={()=>setAnchorTile(x,y)}
            >
            </div>
        {/each}
    {/each}
</div>
