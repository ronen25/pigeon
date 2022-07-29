<script lang="ts">
  import Icon from './Icon.svelte';

  type Style = 'text' | 'icon' | 'textIcon';
  type Variant = 'default' | 'primary' | 'toolbar';

  export let style: Style;
  export let variant: Variant = 'default';
  export let text: String = '';
  export let icon: String = '';
</script>

<div
  class={`flex flex-row items-center justify-center p-1 hover:cursor-pointer
  rounded 
  ${style === 'textIcon' ? 'outline outline-2' : ''}
  ${variant === 'toolbar' ? 'hover:bg-slate-500 active:bg-slate-800' : ''}
  ${variant !== 'toolbar' ? 'focus:ring ring-1' : ''}
  `}>
  <Icon name={icon} width={'24px'} height={'24px'} fill="#FFFFFF" />

  {#if style === 'textIcon' || style === 'text'}
    <div class="ml-2 mr-1">
      {text}
    </div>
  {/if}
</div>
