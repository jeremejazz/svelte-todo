<li class="todo-list list-item-view">
    <span>
      <button class="btn btn-done fa-solid fa-square"></button>
      <span>First Todo</span>
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