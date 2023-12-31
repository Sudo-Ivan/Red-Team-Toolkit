<script lang="ts">
  export let category: string;
  export let tools: { name: string; description: string }[] = [];
</script>

<article class="category">
  <h2>{category}</h2>
  <ul>
    {#each tools as tool}
      <li>
        <strong>{tool.name}</strong>: {tool.description}
      </li>
    {/each}
  </ul>
</article>

<style>
  .category {
    background: rgba(255, 255, 255, 0.1);
    margin-bottom: 2em;
    padding: 1em;
    border-radius: 10px;
  }
  h2 {
    color: #e0e0e0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    margin: 0.5em 0;
    color: #c0c0c0;
  }
</style>
