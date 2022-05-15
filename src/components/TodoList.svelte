<script>
  import TodoInput from "./TodoInput.svelte";
  import List from "./List.svelte";

  let items = [];

  const genRandomId = () => {
    return Math.random().toString(36).slice(2);
  };

  const createItem = (item_value) => {
    items.push({
      id: genRandomId(),
      value: item_value,
      done: false,
    });
    items = [...items];
    console.log({ items });
  };

  const updateItem = (item_id) => {
    for (let i = 0; i < items.length; i++) {
      if (items[i].id === item_id) {
        items[i].done = true;
        break;
      }
    }
    items = [...items];
  };

  const deleteItem = (item_id) => {
    let deleteIndex = -1;
    for (let i = 0; i < items.length; i++) {
      if (items[i].id === item_id) {
        deleteIndex = i;
        break;
      }
    }
    if (deleteIndex !== -1) {
      items.splice(deleteIndex, 1);
      items = [...items];
    }
  };
</script>

<main>
  <div class="todo-input-wrapper">
    <TodoInput {createItem} {updateItem} {deleteItem} />
    <List list_items={items} {updateItem} {deleteItem} />
  </div>
</main>

<style>
  main {
    display: flex;
    justify-content: space-between;
    width: 500px;
    margin: 0 auto;
  }
</style>
