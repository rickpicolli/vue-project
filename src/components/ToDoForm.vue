<template>
<form @submit.prevent="addTodo">
    <h2 class="label-wrapper">
        <label for="new-todo-input" class="label__lg">
        What needs to be done?
    </label>
    </h2>
    <input type="text" id="new-todo-input" name="new-todo" autocomplete="off" v-model.lazy.trim="label" class="input__lg" />
    <button type="submit" class="btn btn__primary btn__lg"> Add </button> 
</form>
  
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            label: ""
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();

            if(this.label === "") {
                return;
            }
            this.$emit('todo-added', this.label);
        }
    }
};
</script>

<style>

</style>