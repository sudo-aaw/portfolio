<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
	import '../app.css';
	import {page} from '$app/stores'

	$:pageName = getPageNameFromURL(String($page.url))

	function getPageNameFromURL(url:string){
		const posOfLastSlash = url.lastIndexOf("/");
		const pageName = url.slice(posOfLastSlash+1);
		return pageName;
    }
</script>

<Navbar {pageName}/>
<slot></slot>


