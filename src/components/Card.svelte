<script>
    export let path
    export let alt
    export let sold = false
</script>

<div class="card">
    <img src = {path} alt = {alt} />
    {#if sold}
    <div class="sold">
        <div class="text">
            sold
        </div>
    </div>
    {/if}
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

    .card .sold {
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
        top: 50%;
        left: 50%;
        -webkit-transform: translateX(-50%) translateY(-50%);
        transform: translateX(-50%) translateY(-50%);
        background-color: rgba(0, 0, 0, 0.4);
    }

    .card .sold .text {
        font-size: 3rem;
        color: white;
        text-transform: uppercase;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
    
</style>