<template>
<div>
    <div class="row">
      <input
        @change="todoTextChange"
        v-bind:value="todoText"
        class="form-control"
        type="text"
      />
      <button @click="addTodoI" class="btn btn-primary">新增</button>
    </div>
  </div>
  </template>



<script >
import { mapActions } from "vuex";
import { v1 } from "uuid";
export default {
  data() {
    return {
      todoText: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    addTodoI() {
      this.addTodo({
        id: v1(),
        title: this.todoText,
        complete: false
      });
      this.todoText = "";
    }
  }
};
</script>



<style scoped>
.btn{
  margin-top: 1rem;
}
</style>
