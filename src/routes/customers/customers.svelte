<script>
    import image from "../../lib/images/admin.jpg";


    let customers = [
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        {
            image: image,
            name: "John Doe",
            date: "14/02/2024",
            revenue: "$200"
        },
        
        
    ];

</script>

<div class="container">
    <div class="header">
        <p>Name</p>
        <p>Date Joined</p>
        <p>Money Saved</p>
    </div>
    <div class="users">
        {#each customers as {image, name, date, revenue}}
        <div class="user">
            <div class="name">
                <img src="{image}" alt="profile" />
                <p>{name}</p>
            </div>
            <p class="date">{date}</p>
            <p class="money">{revenue}</p>
        </div>
        {/each}
        </div>
</div>


<style>
    img{
        width: 40px;
        height: 40px;
        border-radius: 30px;
    }

    .container{
        margin-top: 30px;
        box-shadow: 0px 0px 4px 0px;
        width: 800px;
        height: 500px;
        border-radius: 10px;
        padding: 20px;
        overflow: auto scroll;
    }

    .container::-webkit-scrollbar{
        width: 7px;
    }

    .container::-webkit-scrollbar-thumb{
        background-color: black;
        border-radius: 30px;
    }

    .header{
        display: flex;
        justify-content: space-around;
        color: grey;
    }

    .users{
        margin: 20px 0px;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        gap: 20px;
        
    }

    .user{
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        font-weight: 600;
    }
    .name{
        display: flex;
        justify-content: space-between;
        width: 140px;
        margin-left: -100px;
        align-items: center;
    }

    .date{
        margin-left: -70px;
    }

    .money{
        margin-left: -20px;
    }
</style>