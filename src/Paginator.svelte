<script>
  export let items = [];
  export let visibleindex = 0;
</script>

<style>
  paginator-item:before {
    content: "\25CF";
    font-size: 20px;
  }
  .active {
    color: orange;
  }
</style>

<paginator>
  {#if items}
    {#each items as item, index}
      <paginator-item
        class:active={visibleindex === index}
        on:click={() => (visibleindex = index)} />
    {/each}
  {/if}
</paginator>
