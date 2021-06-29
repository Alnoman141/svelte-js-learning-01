<script>
    import ThisSimple from './ThisSimple.svelte';

    let myComp;

    function updateFromOutside(){
        myComp.update();
    }
</script>

<ThisSimple bind:this="{myComp}" />
<button on:click="{updateFromOutside}">Outside</button>