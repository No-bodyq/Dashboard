<script>
    export let title;
    export let logo;
    export let value;
    export let percentage;

</script>

<div class="card">
    <div class="title">
        <h5>{title}</h5>
        {@html logo}
    </div>
    <h1>{value}</h1>
    {#if percentage}
    <p>{percentage}% since last month.</p>
    {:else}
    <p>{value} users online right now</p>
    {/if}
</div>

<style>
    h5{
        font-weight: bold;
        font-size: 15px;
    }

    h1{
        font-weight: bold;
        font-size: 25px;

    }

    .card{
        background-color: rgb(7, 7, 7);
        color: white;
        padding: 28px;
        width: 255px;
        height:144px;
        border-radius: 4px;
    }

    .title{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    @media screen and (max-width: 1000px){
        .card{
            height: 200px;
        }
    }
</style>