
<script>
  export let totalCount;
  export let remainingCount;
</script>


<div class="app-header">
  <div>{totalCount} Total</div>
  <div class="task-count">{remainingCount} Remaining</div>
</div>

<style>
  .app-header {
    padding: 10px;
    display: flex;
    justify-content: space-between;
  }

  .task-count {
    align-self: center;
  }
</style>
