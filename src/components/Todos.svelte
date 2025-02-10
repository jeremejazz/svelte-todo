<script>
    import Todo from "./Todo.svelte";
</script>

<div class="app-body">
  <ul>
    
    <Todo />
    
  </ul>
</div>

<style>
  ul {
    list-style-type: none;
    -webkit-padding-start: 0;
    padding-left: 0px;
  }
  .app-body {
    flex-grow: 1;
    max-height: 600px;
    overflow-x: hidden;
  }

</style>
