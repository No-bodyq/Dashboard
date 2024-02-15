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
        border:none;
        box-shadow: 0px 0px 4px 0px;
        padding: 30px;
        border-radius: 15px;
    }

    .title{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
</style>