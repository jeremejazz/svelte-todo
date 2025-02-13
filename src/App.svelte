<script>
  import Footer from "./components/Footer.svelte";
  import Header from "./components/Header.svelte";
  import Todos from "./components/Todos.svelte";

  let todos = [
    {
      id: 1,
      itemText: "First Item",
      completed: false,
    },
    {
      id: 2,
      itemText: "Second Item",
      completed: true,
    },
  ];

  let totalCount;


  let remainingCount;
  $: totalCount = todos.length;
  $: remainingCount = todos.filter((todo) => !todo.completed).length;

  const onComplete = (event) => {
    const updateId = event.detail.id;
    console.log("event", event);
    todos.every((todo) => {
      if (todo.id === updateId) {
        todo.completed = !todo.completed;
        return false;
      }
      return true;
    });

    todos = todos; // TODO needs revision
  };

  const addTodo = (event) => {
    const itemText = event.detail.text;
    const id = nextTodoId();
    todos.push({
      id,
      itemText,
      completed: false,
    })

    todos = todos;
  }

  const nextTodoId  = () => {
    if (todos.length === 0){
      return 1;
    }
    return todos[todos.length - 1].id + 1;
  }

 
</script>

<div id="app-container" class="app-container">
  <!-- Header with information -->
  <Header {totalCount} {remainingCount} />
  <!-- List of actual todos -->

  <Todos {todos} on:completed={onComplete} />
  <!-- Add form at bottom -->
  <Footer on:addTodo={addTodo} />
</div>

<style>
  .app-container {
    width: 400px;
    min-height: 500px;
    background-color: #282c34;
    box-shadow: 0 20px 80px rgba(0, 0, 0, 0.6);
    background: radial-gradient(circle, #282c34 0%, rgba(40, 48, 56, 1) 100%);
    position: relative;
    border-radius: 1em;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  ::placeholder {
    opacity: 0.3;
  }
</style>
