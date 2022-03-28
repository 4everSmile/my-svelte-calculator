<style>
    .display-input {
        padding: 12px 20px;
        font-size: 150%;
    }
</style>

<script>
    export let value;
</script>

<p class="text-align-center">
    <input class="display-input" type="text" readonly bind:value={value} />
</p>
