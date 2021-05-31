<script>
    let src = 'https://svelte.dev/svelte-logo-horizontal.svg';
    let blog = `
    <img src="${src}" width="400" alt="Logo">
        <h2>Hello Svelte World</h2>
        <p><strong>Lorem ipsum</strong> dolor sit amet consectetur adipisicing elit. Autem, architecto unde eligendi vero at atque ullam accusantium facilis magni <b>repudiandae</b> eius quibusdam exercitationem mollitia harum ea nihil id debitis delectus.</p>
    `;
</script>

{@html blog}