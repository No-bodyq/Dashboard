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
            name: "Overview", href: "/", icon: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 256 256"><path d="M120,56v48a16,16,0,0,1-16,16H56a16,16,0,0,1-16-16V56A16,16,0,0,1,56,40h48A16,16,0,0,1,120,56Zm80-16H152a16,16,0,0,0-16,16v48a16,16,0,0,0,16,16h48a16,16,0,0,0,16-16V56A16,16,0,0,0,200,40Zm-96,96H56a16,16,0,0,0-16,16v48a16,16,0,0,0,16,16h48a16,16,0,0,0,16-16V152A16,16,0,0,0,104,136Zm96,0H152a16,16,0,0,0-16,16v48a16,16,0,0,0,16,16h48a16,16,0,0,0,16-16V152A16,16,0,0,0,200,136Z"/></svg>`
        },
        {
            name: "Customers", href: "/customers", icon: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-people-fill" viewBox="0 0 16 16">
                <path d="M7 14s-1 0-1-1 1-4 5-4 5 3 5 4-1 1-1 1zm4-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6m-5.784 6A2.24 2.24 0 0 1 5 13c0-1.355.68-2.75 1.936-3.72A6.3 6.3 0 0 0 5 9c-4 0-5 3-5 4s1 1 1 1zM4.5 8a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5"/>
              </svg>`
        },
        {
            name: "Profile", href: "/profile", icon: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-person-fill" viewBox="0 0 16 16">
                <path d="M3 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6"/>
              </svg>`
        },
        {
            name: "Settings", href: "/settings", icon: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-gear-fill" viewBox="0 0 16 16">
                <path d="M9.405 1.05c-.413-1.4-2.397-1.4-2.81 0l-.1.34a1.464 1.464 0 0 1-2.105.872l-.31-.17c-1.283-.698-2.686.705-1.987 1.987l.169.311c.446.82.023 1.841-.872 2.105l-.34.1c-1.4.413-1.4 2.397 0 2.81l.34.1a1.464 1.464 0 0 1 .872 2.105l-.17.31c-.698 1.283.705 2.686 1.987 1.987l.311-.169a1.464 1.464 0 0 1 2.105.872l.1.34c.413 1.4 2.397 1.4 2.81 0l.1-.34a1.464 1.464 0 0 1 2.105-.872l.31.17c1.283.698 2.686-.705 1.987-1.987l-.169-.311a1.464 1.464 0 0 1 .872-2.105l.34-.1c1.4-.413 1.4-2.397 0-2.81l-.34-.1a1.464 1.464 0 0 1-.872-2.105l.17-.31c.698-1.283-.705-2.686-1.987-1.987l-.311.169a1.464 1.464 0 0 1-2.105-.872zM8 10.93a2.929 2.929 0 1 1 0-5.86 2.929 2.929 0 0 1 0 5.858z"/>
              </svg>`
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


</style>