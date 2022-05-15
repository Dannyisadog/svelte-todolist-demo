<script>
  export let createItem;
  let input_value = "";

  const createHandler = () => {
    if (!input_value) return;
    createItem(input_value);
    input_value = "";
  };
</script>

<main>
  <input id="todo-input" type="text" bind:value={input_value} />
  <div class="create-item-btn" on:click={createHandler}>create</div>
</main>

<style>
  main {
    display: flex;
    justify-content: center;
  }
  #todo-input {
    width: 100%;
    height: 30px;
  }
  .create-item-btn {
    margin-left: 10px;
    width: 30%;
    max-width: 80px;
    min-width: 60px;
    color: white;
    background-color: #1b51b4;
    border: 0;
    cursor: pointer;
    height: 30px;
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5px 0;
  }
</style>
