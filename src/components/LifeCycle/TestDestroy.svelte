<script>
    import {onDestroy} from 'svelte';

    let counter = 0;

    let myInterval = setInterval(() => {
        counter+=1;
        console.log(counter);
    }, 1000);

    function removeInterval(){
        onDestroy(() => {
            clearInterval(myInterval);
        })
    }
    removeInterval();
</script>

<h1>{counter}</h1>