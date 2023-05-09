<template>
    <div>
      <ul class="row justify-content-center my-3">
        <li>
          <button type="button" @click="changeTab" :class="{active:completed}">完成</button>
          <button @click="changeTab" :class="{active:!completed}">未完成</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import { mapGetters, mapActions } from "vuex";
  export default {
    computed: {
      ...mapGetters(["completed"])
    },
    methods: {
      ...mapActions(["changeCompleted"]),
      changeTab() {
        this.changeCompleted();
      }
    }
  };
  </script>
  
  <style scoped>
  ul {
    list-style-type: none;
    display: flex;
  }
  button {
    outline: none;
    border: none;
    border-radius: 12% ;
    padding: 1rem;
    color: #000;
    margin: 0.2rem 0.5rem;
    
  }
  button:hover {
    outline: none;
    background-color: rgb(194, 243, 227);
  }
  .active {
    outline: none;
    color: white;
    background-color: rgb(0, 202, 135);
  }
  .active:hover {
    outline: none;
    border: none;
    color: white;
    background-color: rgb(0, 202, 135);
  }
  </style>