<script>
    import Hunger from './Hunger.svelte';
    let colors = [
        {id: 1, name: 'green'},
        {id: 2, name: 'red'},
        {id: 3, name: 'yellow'},
        {id: 4, name: 'blue'},
    ]
    let data = {
        hungerStatus : 'Hungry',
        hungryPerson : 'Noman',
    }
    
    function sum(a, b){
        return a+b;
    }
    
</script>


<h3>{data.hungerStatus}</h3>
<Hunger data="{data}" colors="{colors}" name="Noman" sum="{sum(1,2)}" />

