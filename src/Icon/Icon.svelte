<script>
  /**
   * Specify the icon from `carbon-icons-svelte` to render
   * Icon size must be 16px (e.g. `Add16`, `Task16`)
   * @type {typeof import("carbon-icons-svelte/lib/Add16").default} [render]
   */
  export let render = undefined;

  /**
   * Set to `true` to display the skeleton state
   * @type {boolean} [skeleton=false]
   */
  export let skeleton = false;

  import IconSkeleton from "./Icon.Skeleton.svelte";
</script>

{#if skeleton}
  <IconSkeleton
    {...$$restProps}
    on:click
    on:mouseover
    on:mouseenter
    on:mouseleave
  />
{:else}
  <svelte:component
    this="{render}"
    {...$$restProps}
    on:click
    on:mouseover
    on:mouseenter
    on:mouseleave
  />
{/if}
