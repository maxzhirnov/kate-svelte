<script>
    export let path
    export let alt
</script>

<div class="card">
    <img src = {path} alt = {alt} />
</div>

<style>
    .card {
        position: relative;
    }
    
    .card img {
        width: 100%;
        object-fit:contain;
        display: block;
    }
    
</style>