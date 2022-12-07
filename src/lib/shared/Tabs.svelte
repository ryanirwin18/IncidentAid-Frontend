<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let activeItem;
  export let items;
</script>

<div class="tabs">
  <ul>
    {#each items as item}
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li on:click={() => dispatch('tabChange', item)}>
        <div class:active={item === activeItem}>{item}</div>
      </li>
    {/each}
  </ul>
</div>

<style>
.tabs ul{
  padding: none;
  margin-right: 50px;
}
.tabs li{
  text-align: center;
  text-decoration: underline;
  color: #9C3D00;
  list-style-type: none;
  padding: 3px;
  margin: 5px;
  cursor: pointer;
}
</style>
