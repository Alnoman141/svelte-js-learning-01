<script>
    function handleSubmit(e){
        console.log('submited')
        e.preventDefault();
    }
</script>

<main>
    <form action="/somthing">
        <input placeholder="Fill Me" type="text">
        <button type="submit" on:click="{handleSubmit}">Submit</button>
    </form>
</main>