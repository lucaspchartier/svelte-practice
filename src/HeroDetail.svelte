<script>
    export let hero;
</script>

<style>

</style>

<div>
    <div><label for="name">Name</label>
    <input type="text" name="name" bind:value={hero.name}></div>
</div>