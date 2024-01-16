<script>
    import Card from "./Card.svelte";
    import Overlay from "./Overlay.svelte";

    // https://storage.yandexcloud.net/kzart/
    let imagesPath = 'https://storage.yandexcloud.net/kzart/'
    let items1 = [
        {id: 'svoboda.webp', alt: 'alt', description: 'масло, карандаш/холст на подрамнике/40х50'},
        {id: 'snake.webp', alt: 'alt', description: 'масло/холст на подрамнике/40х50'},
        {id: 'teddy.webp', alt: 'alt', description: 'масло/холст картонный в раме/30х40'},
        {id: 'father.webp', alt: 'alt', description: 'масло/холст на подрамнике/50х60'},
    ]
    let items2 = [
        {id: 'lady.webp', alt: 'alt', description: 'масло/холст на подрамнике/60х80'},
        {id: 'cigs.webp', alt: 'alt', description: 'масло/холст картонный/30х20'},
        {id: 'nebudi.webp', alt: 'alt', description: 'масло/холст на подрамнике/33х23'},
        {id: 'apple.webp', alt: 'alt', description: 'масло/холст на подрамнике/40х30'},
        {id: 'max.webp', alt: 'alt', description: 'масло/холст картонный/30х40'},
        {id: 'wakey.webp', alt: 'alt', description: 'масло/холст картонный в раме/40х30'},
    ]

    let selectedImage = null;
    function openImage(image) {
        image.src = imagesPath + image.id
        selectedImage = image;
        document.body.style.overflow = 'hidden';
    }

</script>

<div class="container">
    <div class="items">
        <div class="left">
            {#each items1 as item}
            <div class="item" 
                on:click={() => openImage(item)} 
                on:keydown={() => openImage(item)}>
                <Card path={imagesPath+item.id} alt={item.alt} />
            </div>
            {/each}
        </div>
        <div class="right">
            {#each items2 as item}
            <div class="item" 
                on:click={() => openImage(item)} 
                on:keydown={() => openImage(item)}>
                <Card path={imagesPath+item.id} alt={item.alt} />
            </div>
            {/each}
        </div>
    </div>
</div>
{#key selectedImage}
    <Overlay image={selectedImage} />
{/key}


<style>
    .container {
        display: flex;
		justify-content: center;
    }
    .items {
        display: flex;
        max-width: 800px;
        gap: 2rem;
    }
    .item {
        margin-bottom: 2rem;
    }
  /* Media query for mobile view */
  @media (max-width: 600px) {
    .items {
        flex-direction: column;
    }
  }
  
</style>