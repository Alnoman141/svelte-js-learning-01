<script>
import App from "../App.svelte";

    async function fetchUser(){
        const response = await fetch('https://api.github.com/users/Alnoman141');
        return response.json();
    }
</script>

{#await fetchUser()}
    <p>Loading...</p>
{:then response } 
    <img src={response.avatar_url} alt="" width="100">
    <h3>{response.name}</h3>
{/await}