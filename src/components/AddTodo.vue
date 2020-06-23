<template>
  <div>
    <h3>Add Tasks</h3>
    <div class="add">
      <form @submit="onSubmit">
        <b-input type="text" v-model="title" placeholder="Add Task"></b-input>
        <input type="submit" value="Submit" class="btn btn-outline-info">
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #09acec;
  outline: 0;
}

input[type="submit"] {
  flex: 2;
  background: #0396f8;
  color: #fff;
  border: 1px #09acec solid;
  cursor: pointer;
}
</style>
