<script>
    import Overlay from "./Overlay.svelte";
    import Collection from "./Collection.svelte";

    // https://storage.yandexcloud.net/kzart/
    let imagesPath = 'https://storage.yandexcloud.net/kzart/'
    
    let itemSets = [
        [
            {id: 'svoboda.webp', alt: 'alt', description: 'масло, карандаш/холст на подрамнике/40х50', src: imagesPath+'svoboda.webp'},
            {id: 'nebudi.webp', alt: 'alt', description: 'масло/холст на подрамнике/33х23', src: imagesPath+'nebudi.webp'},
        ],
        [
            {id: 'snake.webp', alt: 'alt', description: 'масло/холст на подрамнике/40х50', src: imagesPath+'snake.webp'},
            {id: 'apple.webp', alt: 'alt', description: 'масло/холст на подрамнике/40х30', src: imagesPath+'apple.webp'},
            {id: 'lady.webp', alt: 'alt', description: 'масло/холст на подрамнике/60х80', src: imagesPath+'lady.webp'},
        ],
        [
            {id: 'cigs.webp', alt: 'alt', description: 'масло/холст картонный/30х20', src: imagesPath+'cigs.webp'},
            {id: 'wakey.webp', alt: 'alt', description: 'масло/холст картонный в раме/40х30', src: imagesPath+'wakey.webp'},
            {id: 'bear2.webp', alt: 'alt', description: 'масло/холст картонный в раме/50х40', src: imagesPath+'bear2.webp'},
        ],
        [
            {id: 'max.webp', alt: 'alt', description: 'масло/холст картонный/30х40', src: imagesPath+'max.webp'},
            {id: 'father.webp', alt: 'alt', description: 'масло/холст на подрамнике/50х60', src: imagesPath+'father.webp'},
        ],
        [
            {id: 'ladyback.webp', alt: 'alt', description: 'масло, акрил, холст на подрамнике/40х50', src: imagesPath+'ladyback.webp'},
            {id: 'cama.webp', alt: 'alt', description: 'масло, акрил, холст на подрамнике/40х50', src: imagesPath+'cama.webp'},
        ]
    ]

    let selectedImage = null;

    function openImage(image) {
        image.src = imagesPath + image.id
        selectedImage = image;
        document.body.style.overflow = 'hidden';
    }

    function handleCollectionItemClick(event) {
        openImage(event.detail.item)
    }

</script>

<div class="container">
    <div class="content">
        {#each itemSets as set}
            <Collection items={set} on:itemClick={handleCollectionItemClick}/>
        {/each}
    </div>
</div>

{#key selectedImage}
    <Overlay image={selectedImage} />
{/key}

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .content {
        max-width: 800px;
    }

    @media (max-width: 600px) {}
</style>