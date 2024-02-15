<script>
    import Calender from "../calender.svelte";
    import Customers from "./customers.svelte";

</script>


<div class="top">
    <h1>Customers</h1>
    <Calender />
</div>

<Customers />


<style>
    h1{
        font-weight: bold;
        font-size: 30px

    }
    .top{
        margin-top:20px;
        margin-right:60px;
        display:flex;
        justify-content:space-between;
    }
</style>
