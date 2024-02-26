<script>
    import { onMount } from 'svelte';
    import { page } from '$app/stores';
    
 
    $: currentPageUrl = $page.url.pathname;
        
    onMount(() => {
        currentPageUrl = $page.url.pathname;
    })

    export let expanded;

    function expand(){
        currentPageUrl = $page.url.pathname;
        expanded = !expanded;
    }

    const NAVIGATION_LIST = [
        {
            name: "Overview", href: "/", icon: `<span class="material-symbols-outlined">home</span>`
        },
        {
            name: "Customers", href: "/customers", icon: `<span class="material-symbols-outlined">group</span>`
        },
        {
            name: "Profile", href: "/profile", icon: `<span class="material-symbols-outlined">person</span>`
        },
        {
            name: "Settings", href: "/settings", icon: `<span class="material-symbols-outlined">settings</span>`
        },
        
    ]


</script>


<div id="expand-container" class:wide={expanded == true}><a href={currentPageUrl} id="expand" class:expanded on:click={expand}>
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 256 256"><path d="M237.66,133.66l-32,32A8,8,0,0,1,192,160V136H64v24a8,8,0,0,1-13.66,5.66l-32-32a8,8,0,0,1,0-11.32l32-32A8,8,0,0,1,64,96v24H192V96a8,8,0,0,1,13.66-5.66l32,32A8,8,0,0,1,237.66,133.66Z"></path></svg>
</a>
</div>
    <div class="side">
        <ul>
            {#each NAVIGATION_LIST as {name, href, icon}}
                <li class:wide={expanded == true}>
                    <a {href} class:expanded class={`${href === currentPageUrl ? 'highlight' : ''}`}>
                        {@html icon}
                        {name}
                    </a>
                </li>
            {/each}
        </ul>
        <ul>
            <li class:wide={expanded == true}><a href="/logout" class:expanded>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 256 256"><path d="M116,216a12,12,0,0,1-12,12H48a20,20,0,0,1-20-20V48A20,20,0,0,1,48,28h56a12,12,0,0,1,0,24H52V204h52A12,12,0,0,1,116,216Zm108.49-96.49-40-40a12,12,0,0,0-17,17L187,116H104a12,12,0,0,0,0,24h83l-19.52,19.51a12,12,0,0,0,17,17l40-40A12,12,0,0,0,224.49,119.51Z"></path></svg>
            Sign Out
            </a></li>
        </ul>
    </div>
    

<style>
    ul{
        list-style: none;
        display: flex;
        flex-direction: column;
        gap: 20px;
        padding: 0px;
        margin: 50px 10px 0px 10px;
        justify-content: center;
        align-items: center;
    }

    a{
        text-decoration: none;
        padding: 15px;
        color: black;
        border-radius: 50px;
        width: 100px;
        overflow: hidden;
        font-size: 0px;
        padding-left: 25px;
    }

    li{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        text-align: center;
        border-radius: 50px;
        width: 70px;
        animation-name: collapse;
        animation-duration: 1s;
    }

    a{
        transition: width 1s, font-size 1s ease;

    }

    @keyframes collapse{
        from {width: 200px;}
        to {width: 70px;}
    }


    a:hover{
        color: white;
        background-color: black;
    }
    
    li > a{
        display:flex;
        gap: 10px;
    }

    .side{
        display:flex;
        flex-direction:column;
        gap:200px;
    }


    .highlight {
        background-color: black;
        color: white;
    }

    #expand-container{
        display: flex;
        padding: 0px;
        justify-content: center;
        align-items: center;
    }

    #expand{
        width: 20px;
        padding-right: 40px;
    }

    #expand:hover{
        background-color: black;
    }

    .expanded{
        font-size: 15px;
        width: 200px;
        text-align: left;
    }


    .wide{
        animation-name: expand;
        animation-duration: 1s;
        width: 200px;
    }

    @keyframes expand{
        from {width: 70px;}
        to {width: 200px;}
    }

    @media screen and (max-width: 1000px){
		ul{
            flex-direction: row;
            margin: -40px 10px;
        }
        .side{
            flex-direction: row;
        }

        .wide{
            animation-name: expand;
            animation-duration: 1s;
            width: 150px;
        }
        @keyframes expand{
            from {width: 70px;}
            to {width: 150px;}
        }
        @keyframes collapse{
            from {width: 150px;}
            to {width: 70px;}
        }
	}


</style>