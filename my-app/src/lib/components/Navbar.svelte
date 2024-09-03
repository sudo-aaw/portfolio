
<script lang="ts">
	import { onMount } from 'svelte';


    export var pageName = "";

    // $:pageName = getPageNameFromURL(String($page.url))


    function getPageNameFromURL(url:string){
        const posOfLastSlash = url.lastIndexOf("/");
        const pageName = url.slice(posOfLastSlash+1);
        return pageName;
    }

    // const pageExtension= $page.url.pathname.slice($);

    const currentPageClass = "text-foreground hover:text-foreground transition-colors py-4";
    const inactivePageClass = "text-muted-foreground hover:text-foreground transition-colors py-4"

    onMount(()=>{
        const pageLinks = Array.prototype.slice.call(document.getElementsByTagName("a"));
        pageLinks.forEach(pageLink => {
            const hrefPageName = getPageNameFromURL(pageLink.href);
            if(hrefPageName===pageName){
                pageLink.className=currentPageClass;
            }else{
                pageLink.className=inactivePageClass;
            }
        })
    })


</script>

<div class="display flex content-center justify-center border-b-2 bg-opacity-70" id="navbar">
    <nav
    class="hidden flex-col gap-6 text-lg font-medium md:flex md:flex-row md:items-center md:gap-5 md:text-sm lg:gap-6 bg-white border-y:red"
    >
    <a href="Home" class={inactivePageClass}>
      Home
    </a>
    <a href="Projects" class={inactivePageClass}>
        Projects
    </a>
    <a href="Career" class={inactivePageClass}>
        Career
    </a>
    <a href="Certificates" class={inactivePageClass}>
        Certificates
    </a>
    <a href="Education" class={inactivePageClass}>
        Education
    </a>
    </nav>
</div>
