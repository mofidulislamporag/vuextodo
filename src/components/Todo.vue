<template>
	<div style="margin:5px auto; width:250px; ">
	<div style="display:flex; justify-content:space-between">
	<span :class="{completed: todo.completed}" @click="toggleTodoStatus">{{ todo.title }}</span>
	<button @click="deleteTodo">Delete</button>
	</div>
	</div>

</template>

<script> 
export default {
  props: ["todo"],

  methods: {
    deleteTodo(){
      this.$store.dispatch("deleteTodo", this.Todo);
    },

    toggleTodoStatus(){
      this.$store.dispatch("toggleTodoStatus", this.Todo);
    }
  }
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>
