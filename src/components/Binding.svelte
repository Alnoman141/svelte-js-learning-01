<script>
    let width = 400;
    let imgUrl;
    let isChecked = false;
</script>

<main>
    <input type="text" bind:value="{width}" disabled={isChecked}>
    <input type="range" bind:value="{width}" disabled={isChecked} min="100" max="2000"> 
    <input type="checkbox" bind:checked={isChecked}><br />

    <div>
        <label>
            <input disabled={isChecked} type="radio" bind:group="{imgUrl}" value="https://i.ytimg.com/vi/SVJsBovH7UI/maxresdefault.jpg"> Mr. Bean
        </label>
        <label>
            <input disabled={isChecked} type="radio" bind:group="{imgUrl}" value="https://i.ytimg.com/vi/bNd5xfqVw1M/maxresdefault.jpg"> Doraemon
        </label>
    </div>
    <div>
        <select bind:value="{imgUrl}" disabled={isChecked}>
            <option value="https://i.ytimg.com/vi/SVJsBovH7UI/maxresdefault.jpg">Mr. Bean</option>
            <option value="https://i.ytimg.com/vi/bNd5xfqVw1M/maxresdefault.jpg">Doraemon</option>
        </select>
    </div>

    <img src="{imgUrl}" alt="" {width}>
</main>