<script lang="ts">
  import Button from './components/Button.svelte';

  type RequestItem = {
    title: string;
    url: string;
  };

  let requests: Array<RequestItem> = [];
  let searchTerm = '';
</script>

<div class="bg-slate-300 h-full flex flex-col">
  <div class="flex flex-row p-2 bottom-2 bg-blue-900">
    <input class="h-8 p-2 flex-1" bind:value={searchTerm} />
    <div class="pl-2">
      <Button style="icon" variant="toolbar" icon="file-earmark-plus" />
    </div>
  </div>

  {#if requests.length !== 0}
    <div>LIST HERE</div>
  {:else}
    <div class="flex justify-center items-center flex-1">LA</div>
  {/if}
</div>
