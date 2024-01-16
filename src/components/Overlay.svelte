<script>
    export let image = null;
  
    function closeOverlay() {
      image = null;
      document.body.style.overflow = '';
    }
  </script>
  
  {#if image}
    <div class="overlay" 
    on:click={closeOverlay} 
    on:keydown={closeOverlay}>
      <img class="full-size-image" src={image.src} alt={image.alt}>
      <div class="description">{image.description}</div>
      <span class="close-button">⨯</span>
    </div>
  {/if}
  
  <style>
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.9);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
  
    .full-size-image {
      max-width: 90%;
      max-height: 90%;
    }

    .description {
        color: white;
    }
    .close-button {
        color: rgb(214, 214, 214);
        position: fixed;
        top: .5rem;
        right: 2rem;
        cursor: pointer;
        font-size: 3rem;
    }

    .close-button:hover {
        color: white;
        font-size: 3.1rem;
    }
  </style>