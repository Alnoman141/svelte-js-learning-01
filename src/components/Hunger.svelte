<script>
    export let data;
    export let colors;
    export let sum;

    function message(){
        if(data.hungerStatus === 'Hungry'){
            return 'I am Hungry. give me food.';
        } else {
            return  'I am not Hungry. You take the food.';
        }
    }
</script>
<h3>{$$props.name}</h3>
{sum}
<p>{data.hungryPerson} says, '{message()}'</p>
{#each colors as color}
<p>{color.name}</p>
{/each}
