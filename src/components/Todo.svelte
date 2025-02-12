<script>
  import { createEventDispatcher } from "svelte";

  export let itemId;
  export let itemText;
  export let completed;

  let dispatch = createEventDispatcher();

  const clickComplete = (id) => {
    dispatch("completed", {
      id,
    });
  };
</script>

<li class="todo-list list-item-view {completed ? 'completed' : ''}">
  <span>
    <button
      on:click={() => clickComplete(itemId)}
      class="btn btn-done fa-solid {completed ? 'fa-check-square' : 'fa-square' }"
    ></button>
    <span>{itemText}</span>
  </span>
  <button class="btn btn-delete fa-solid fa-trash"></button>
</li>

<style>
  .todo-list:first-of-type {
    border-top: 1px solid rgb(121, 121, 121);
    padding-top: 10px;
  }

  .list-item-view {
    padding-top: 5px;
    padding-bottom: 0px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .completed {
    color: #6a6f75;
    opacity: 0.5;
  }
</style>
