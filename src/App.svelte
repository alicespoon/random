<script>
  import { onMount } from "svelte";
  import Packery from "packery";

  import Card from "./lib/Card.svelte";
  import Header from "./lib/Header.svelte";

  const apiUrl = "https://api.airtable.com/v0/";
  const baseId = "appH98tK7apH08Hlx";
  const tableName = "Instagram";
  const headers = {
    Authorization:
      "Bearer pat0mAKO9RNPHvpVd.ddc4e7b59bdda4265756dde9ada38b41ace0d7a77c251fb08640d1e387aed57d",
  };
  const url = `${apiUrl}${baseId}/${tableName}`;

  let posts = [];

  onMount(() => {
    fetch(url, { headers })
      .then((response) => response.json())
      .then((data) => {
        console.log(data);
        posts = data.records.map((record) => {
          return {
            igurl: record.fields["url"],
            images: record.fields["images"],
          };
        });
        console.log(posts);

      })
      .then(() => {
        const base = document.querySelector("main");
        console.log(base.children);
        const pckry = new Packery(base, {
          gutter: 48,
        });
      })
      .catch((error) => {
        console.error(error);
      });
  });
</script>

<Header />
<main>
  {#each posts as post}
    <Card {...post} />
  {/each}
</main>

<style>
  main {
    display: flex;
    flex-direction: row;
  }
</style>
