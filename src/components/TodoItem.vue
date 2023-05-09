<template>
 <div>
    <div class="row my-3 justify-content-between align-items-center g-0 text-center">
      <h3 v-if="!editing">{{todo.title}}</h3>

      <div v-else class="mr-2 row justify-content-between align-items-center col g-0 text-center">
        <input
          v-bind:value="todoText"
          @change="todoTextChange"
          type="text"
          class="col-7 form-control"
        />
        <div>
          <input :checked="completed" class="mr-1" @change="onCompleted" type="checkbox" />
          <label class="com">完成</label>
        </div>
      </div>
      <div class="row align-items-center">
        <button @click="updateTodoI(todo)" class="btn btn-primary">{{editing?'更新':'修改'}}</button>
        <button @click="deleteTodo(todo.id)" class="btn btn-danger">刪除</button>
      </div>
    </div>
  </div>
</template>

<script scoped>
import { mapActions } from "vuex";
export default {
  props: {
    todo: {}
  },
  data() {
    return {
      todoText: "",
      editing: false,
      completed: false
    };
  },
  methods: {
    ...mapActions(["deleteTodo", "updateTodo", "changeCompleted"]),
    onCompleted() {
      this.completed = this.completed == true ? false : true;
    },
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    updateTodoI(todo) {
      this.editing = this.editing == true ? false : true;
      if (this.editing) {
        this.todoText = todo.title;
        this.updateTodo(todo);
      } else {
        todo.title = this.todoText;
        todo.complete = this.completed;
        this.changeCompleted();
      }
    }
  }
};
</script>

<style scoped>
.btn{
  margin: 0.5rem 0;
}
.com{
  margin: 0.5rem 0.05rem;
}
</style>