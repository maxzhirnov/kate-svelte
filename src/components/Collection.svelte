<script>
    import Card from "./Card.svelte"
    import { createEventDispatcher } from "svelte";

    export let items

    const dispatch = createEventDispatcher()

    function handleClick(item) {
        dispatch('itemClick', {item: item})
    }
</script>

<div class="collection">
    <div class="divider"></div>
    <div class="items">
        {#each items as item}
        <div class="item" 
        on:click={() => handleClick(item)} 
            on:keydown={() => handleClick(item)}>
            <Card path={item.src} alt={item.alt}/>
        </div>
        {/each}
    </div>
</div>

<style>
    .divider {
        width: 100%;
        border-bottom: .5px solid rgb(0, 0, 0);
        margin-bottom: 1rem;
    }
    .items {
        column-count: 2;
        column-gap: 1rem;
        margin-bottom: 1rem;
    }
    .item {
        break-inside: avoid;
        margin-bottom: 1rem;
    }
</style>