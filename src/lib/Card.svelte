<script>
  export let igurl = "";
  export let images = [];
</script>

{#if images.length > 0}
  {#each images as image}
    <a href={igurl} target="_blank">
      <img src={image.url} alt={image.filename} />
    </a>
  {/each}
{/if}

<style>
  img {
    max-width: 100%;
  }
</style>
