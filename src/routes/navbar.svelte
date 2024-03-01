<script>
    import image from "../lib/images/admin.jpg"

    let searchTerm = '';

    function handleSearch(){
        console.log('Searching for: ', searchTerm);
    }
</script>

<nav>
    <div class="search-container">
        <input type="text" id="searchInput" bind:value={searchTerm} placeholder="Enter search term" on:input={handleSearch}/>
        <button on:click={handleSearch}><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">
            <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/>
          </svg></button>
    </div>
    <div class="right">
        <img src="{image}" alt=admin>
        <div class="text">
            <p>theforce289@gmail.com</p>
        </div>

        
    </div>
</nav>

<style>
*{
    font-family: 'Oswald', sans-serif;
}

nav{
    display: flex;
    justify-content: space-between;
    padding-top: 10px;
    margin-right: 60px
}

.search-container {
    display: flex;
    margin-top: 1em;
}

input {
    flex: 1;
    padding: 0.5em;
    width: 500px;
    background-color: rgb(7, 7, 7);
    color: white;
    outline: none;
    border: none;
    border-radius: 20px;
}


button {
    margin-left: -50px;
    padding: 4px 17px;
    cursor: pointer;
    color: white;
    border: none;
    width:10px;
    text-align: center;
    border-radius: 15px;
}

.right{
    display: flex;
    align-items: center;
    gap: 30px;
    margin-right: 10px;
}

img{
    width: 40px;
    height: 40px;
    border-radius: 30px;
}

.text{
    display: flex;
}

p{
    font-size: 15px;
}
</style>