<script>
    export let path
    export let alt
</script>

<div class="item">
    <img src = {path} alt = {alt} />
</div>

<style>
    .item {
        position: relative;
    }
    
    .item img {
        width: 100%;
        object-fit:contain;
        display: block;
    }
    
</style>