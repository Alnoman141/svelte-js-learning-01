<script>
    let user;
    import { onMount } from 'svelte';
    onMount(async () => {
        const data = await fetch("https://api.github.com/users/Alnoman141");
        user = await data.json();
    })
    
</script>

    {#if user}
    <h1>{user.name}</h1>
    {:else}
    <h4>Loading...</h4>    
    {/if}    
