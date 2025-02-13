<script>
  import { createEventDispatcher } from "svelte";

  export let inputText = "";

  const dispatch = createEventDispatcher();
  // enter and button
  /**
   *
   * @param text string
   */
  const addTodo = (text) => {
    dispatch("addTodo");
    
    inputText = "";
  };
</script>

<div class="app-form">
  <input
    bind:value={inputText}
    placeholder="Add Todo.."
    type="text"
    class="input-text"
    name=""
 
  />
  <button on:click={() => addTodo(inputText)} class="btn fa-solid fa-plus"></button>
</div>

<style>
  .app-form {
    margin-bottom: 10px;
    display: flex;
    justify-content: center;
  }

  .input-text {
    height: 40px;
    background: #282c34;
    font-size: 15px;
    border: 1px solid #a2a8ad;
    color: #dce4ec;
    width: 100%;
    margin-right: 15px;
    border-radius: 2em;
    padding: 5px 10px;
    transition: border 250ms ease-out;
  }

  .input-text:focus {
    border: 1px solid #ffffff;
    background: #1d2025;
    outline: none;
    color: #dce4ec;
  }
</style>
