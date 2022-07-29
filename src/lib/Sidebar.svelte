<script lang="ts">
  type RequestItem = {
    title: string;
    url: string;
  };

  let requests: Array<RequestItem> = [];
  let searchTerm = '';
</script>

<div class="bg-slate-300 h-full">
  <div class="flex flex-row p-2 bottom-2 border-b-blue-600 border-b-1 w-full">
    <input bind:value={searchTerm} />
  </div>

  {#if requests.length !== 0}
    <div>LIST HERE</div>
  {:else}
    <div class="flex justify-center items-center h-full">LA</div>
  {/if}
</div>
