        
<script setup>
import { ref, defineEmits, reactive } from 'vue';

const emit = defineEmits(["create-todo"])


// const todo = ref("")

const todoState = reactive({
    todo: "",
    invalid: null,
    errMsg: ""
})

const emitTodo = () => {
    todoState.invalid = null

    if (todoState.todo !== "") {
        emit("create-todo", todoState.todo)
        todoState.todo = ""
        return
    }
    todoState.invalid = true
    todoState.errMsg = "ⓘ This can't be empty"
}

</script>

<template>
    <div class="input-group mb-1">
        <input type="text" class="form-control" v-model="todoState.todo" placeholder="Add your Todo here">
        <button @click="emitTodo()" class="btn btn-success">Create</button>
    </div>
    <div v-show="todoState.invalid" class="text-start">
        <small class="text-danger">{{ todoState.errMsg }}</small>
    </div>
</template>


<style lang="scss" scoped></style>