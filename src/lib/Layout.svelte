<script lang="ts">
  import { Pane, Splitpanes } from 'svelte-splitpanes';
  import Sidebar from './Sidebar.svelte';
</script>

<main>
  <div class="h-screen">
    <Splitpanes theme="my-theme">
      <Pane size={25} minSize={25} maxSize={60}>
        <Sidebar />
      </Pane>
      <Pane>
        <div>LA</div>
      </Pane>
    </Splitpanes>
  </div>
</main>

<style global>
  :global(.splitpanes.my-theme) :global(.splitpanes__pane) {
    background-color: #f8f8f8;
  }
  :global(.splitpanes.my-theme) :global(.splitpanes__splitter) {
    background-color: #ccc;
    position: relative;
    cursor: col-resize;
  }
  :global(.splitpanes.my-theme) :global(.splitpanes__splitter:before) {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    transition: opacity 0.4s;
    background-color: rgba(0, 81, 255, 0.8);
    opacity: 0;
    z-index: 1;
  }
  :global(.splitpanes.my-theme) :global(.splitpanes__splitter:hover:before) {
    opacity: 1;
  }

  :global(.my-theme.splitpanes--vertical)
    > :global(.splitpanes__splitter:before) {
    left: -2px;
    right: -2px;
    height: 100%;
    cursor: col-resize;
  }
  :global(.my-theme.splitpanes--horizontal)
    > :global(.splitpanes__splitter:before) {
    top: -2px;
    bottom: -2px;
    width: 100%;
    cursor: row-resize;
  }
</style>
