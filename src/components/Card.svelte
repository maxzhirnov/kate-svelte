<script>
    export let path
    export let description
    export let alt
</script>

<div class="item">
    <img src = {path} alt = {alt} />
    <div class="hover-info">{description}</div>
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
    .item .hover-info {
        position: absolute;
        text-align: center;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100px;
        background-color: rgba(0,0,0,0.8); /* полупрозрачный черный фон */
        color: white; /* белый текст */
        display: flex;
        justify-content: center; /* центрируем текст по горизонтали */
        align-items: center; /* центрируем текст по вертикали */
        opacity: 0; /* сделать div невидимым по умолчанию */
        transition: opacity 0.5s; /* плавное появление текста */
        }

    .item:hover .hover-info {
        opacity: 1; /* делает div видимым при наведении */
        }
</style>