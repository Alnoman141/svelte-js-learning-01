<script>
    let logedIn = false;
    let replies = [
        {
            time: '1 min ago',
            message: 'I am learning svelte js',
        },
        {
            time: '3 min ago',
            message: 'I think svelte is very famous'
        },
        {
            time: '5 min ago',
            message: 'What do u think about sveltejs'
        }
    ];

    function addNew(){
        replies = [{
            time: 'just now',
            message: 'Svelte js is very cool',
        }, ...replies]
    };

    function remove(index){
        replies = replies.filter((r, i) => i !== index);
    };

    function login(){
        logedIn = true;
    };

    function logout(){
        logedIn = false;
    }
</script>

<main>
    <h2>Let's Talk About SvelteJs</h2>

    {#each replies as reply, index}
    <div>
        <h3>{reply.time}</h3>
        <p>{reply.message}</p>
    </div>
    <button on:click="{() => remove(index)}">Remove</button>
    {/each}
 
    <div>
        {#if logedIn}
        <button on:click="{addNew}">Add New</button>
        <button on:click="{logout}">Logout</button>
        {:else}
        <button on:click="{login}">Login Now</button>
        {/if}
    </div>
</main>