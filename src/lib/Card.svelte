<script>
  export let igurl = "";
  export let images = [];
</script>

{#if images.length > 0}
  {#each images as image}
    <a href={igurl} target="_blank">
      {#if image.type === "image/png"}
        <img src={image.url} alt={image.filename} />
      {:else if image.type === "video/mp4"}
        <video src={image.url} autoplay muted loop playsinline />
      {/if}
    </a>
  {/each}
{/if}

<style>
  img,
  video {
    max-width: 100%;
  }
</style>
