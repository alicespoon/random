<script>
  export let igurl = "";
  export let images = [];
</script>

<main>
  {#if images.length > 0}
    <a href={igurl} target="_blank">
      {#each images as image}
        <img src={image.url} alt={image.filename} />
      {/each}
    </a>
  {/if}
</main>

<style>
  main {
    display: flex;
    flex-direction: row;
  }

  img {
    width: 300px;
  }
</style>
