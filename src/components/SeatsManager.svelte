<script lang="ts">
    import { setContext } from 'svelte'

    export let seatsData;

    setContext('seatsManagerData', seatsData);
</script>

<div>
    <div class="wrapper">
        <slot />
    </div>
</div>

<style>
    .wrapper {
        display: flex;
        max-width: 1400px;
        margin: 0 auto;
        flex-wrap: wrap;
    }
</style>
