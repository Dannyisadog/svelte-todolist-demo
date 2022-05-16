<script>
  export let item, updateItem, deleteItem;
</script>

<main>
  <div class="item-wrapper">
    <div class="todo-value {item.done && 'done'}">{item.value}</div>
    <div class="action-button-wrapper">
      <div
        class="done-button action-button {item.done && 'done'}"
        on:click={!item.done && updateItem(item.id)}
      >
        V
      </div>
      <div class="delete-button action-button" on:click={deleteItem(item.id)}>
        X
      </div>
    </div>
  </div>
</main>

<style>
  .item-wrapper {
    width: 100%;
    height: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #f4f4f4;
    border-radius: 4px;
    padding: 0 8px;
    margin-top: 10px;
    color: #333;
  }
  .todo-value.done {
    text-decoration: line-through;
    color: #bcbcbc;
  }
  .action-button-wrapper {
    display: flex;
    justify-content: space-between;
    width: 70px;
  }
  .action-button {
    width: 30px;
    height: 30px;
    border-radius: 4px;
    color: white;
    font-size: 20px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: 0.3s;
  }
  .action-button.hidden {
    display: none;
  }
  .done-button {
    background-color: #18d288;
  }
  .done-button.done {
    background-color: #a8a8a8;
    cursor: not-allowed;
  }
  .done-button.done:hover {
    background-color: #a8a8a8;
  }
  .done-button:hover {
    background-color: #11a167;
  }
  .delete-button {
    background-color: #e76844;
  }
  .delete-button:hover {
    background-color: #cc4c29;
  }
</style>
