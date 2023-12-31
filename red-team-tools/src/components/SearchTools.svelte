<script lang="ts">
  import { createEventDispatcher } from 'svelte';
  
  const dispatch = createEventDispatcher();

  let searchTerm: string = '';

  const search = () => {
    dispatch('search', { term: searchTerm });
  };
</script>

<div class="search-container">
  <input
    type="text"
    bind:value={searchTerm}
    placeholder="Search tools..."
    on:input={search}
    class="search-input"
  />
</div>

<style>
  .search-container {
    margin-bottom: 1em;
  }
  .search-input {
    width: 100%;
    padding: 0.5em;
    border-radius: 8px;
    border: none;
    background: rgba(255, 255, 255, 0.2);
    color: white;
    font-size: 1em;
  }
</style>
