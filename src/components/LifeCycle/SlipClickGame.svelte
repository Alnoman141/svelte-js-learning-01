<script>
    import {onMount, afterUpdate } from 'svelte';
    let bombs = new Array(50);
    let attemps = 0;
    let randNum = 0;
    let score = 0;
    let interval;
    onMount(() => {
        interval = setInterval(() => {
            randNum = Math.floor(Math.random() * bombs.length)
        }, 1000)
    })
    afterUpdate(() => {
        if(attemps== 10){
            clearInterval(interval);
            alert('Game Over!')
        }
    })
    function handleClick(index){
        if(index === randNum){
            score += 1;
            bombs = [...bombs.slice(0, index), ...bombs.slice(index +1)]
        } else {
            attemps+=1;
        }
        
    }
</script>


<main style="width: 50%; margin: 0 auto">
    <h1>Slip Click Game</h1>
    <h3>Score: {score} | Attemps: {attemps}</h3>
    {#each bombs as bomb, i}
        <span style="{i == randNum ? '' : 'opacity: 0.3;'}" on:click="{() => handleClick(i)}" class="bomb-size">💣</span>
    {/each}
</main>

<style>
    .bomb-size {
        font-size: 50px;
        cursor: pointer;
    }
</style>