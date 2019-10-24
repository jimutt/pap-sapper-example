<script>
  import { onMount } from "svelte";
  import PickAPlace from "svelte-pick-a-place";

  let leaflet;

  onMount(async () => {
    leaflet = (await import("leaflet")).default;
  });
</script>

<style>
  .pick-a-place-wrapper {
    width: 100%;
    height: 800px;
  }
</style>

<svelte:head>
  <title>Sapper project template</title>
</svelte:head>

<div class="pick-a-place-wrapper">
  {#if leaflet != null}
    <PickAPlace {leaflet} on:update={() => console.log('Update!')} />
  {/if}
</div>
