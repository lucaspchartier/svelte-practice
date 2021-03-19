<script>
    export let heroes;
</script>

<h1>Heroes List</h1>

<style>
    ul {
        list-style-type: none;
        padding: 4px;
    }
    ul > li {
        padding: 4px;
        cursor: pointer;
    }
    .selected {
        background-color: yellow;
    }
    .row {
        margin: 10px;
        box-shadow: 0 0 5px gray;
        padding: 10px 20px;
    }
    .error {
        background: rgb(255, 219, 219);
        padding: 10px 20px;
    }
</style>