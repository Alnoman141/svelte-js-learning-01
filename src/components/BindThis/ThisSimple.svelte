<script>
    let myTag;
    let data = "";
    export function update(){
        myTag.style.color = 'blue';
        myTag.innerHTML = `<h1>${data}</h1>`;
        data = "";
    }
</script>
<main>
    <p bind:this="{myTag}">Hello</p>
    <input type="text" bind:value="{data}"> <br />
    <button on:click="{update}">Update</button>
</main>