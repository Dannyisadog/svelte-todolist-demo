<script>
  export let updateItem, deleteItem;
  import ListItem from "./ListItem.svelte";

  export let list_items;
</script>

<main>
  {#each list_items as item}
    <ListItem {item} {updateItem} {deleteItem} />
  {/each}
</main>
