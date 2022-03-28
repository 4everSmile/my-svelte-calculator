<style>
    .calc-button {
        min-width: 80px;
        min-height: 80px;
        font-size: 30px;
        margin-bottom: 0;
    }

    .calc-button-result {
        min-width: 165px;
        min-height: 80px;
        font-size: 30px;
        background-color: #F08080;
    }

</style>

<script>
    export let text;
    export let className = "calc-button";
    export let onClick;
</script>

<button class={className} on:click={onClick}>{text}</button>
