<template>
    <div class="todo-list">
        <h2>{{ category }}</h2>
        <input type="text" v-model="newTodo" v-on:keyup.enter="addTodo(newTodo)">
        <button @click="addTodo(newTodo)">추가하기</button><br>
        <li v-for="todo in todos" :class="{completed: todo.completed}" :key="todo.id">
        <input type="checkbox" v-model="todo.completed">
            {{ todo.content }}
        <button @click="removeTodo(todo)">삭제하기</button>
        </li>
    </div>
</template>

<script>
export default {
    props: {
        category: {
        type: String,
        required: true
        }
    }, // 하위 컴포넌트로 데이터 전송 +검증
    // data를 펑션으로 만들고 object를 인자로 넘긴다.
    data() {
        return {
        todos: [],
        newTodo: ''
        }
    },
    methods: {
        addTodo(newTodo){
        this.todos.push({
            id: Date.now(),
            content: newTodo,
            completed: false,
        })
        this.newTodo = ''
        },
        removeTodo(removeTodo){
        this.todos = this.todos.filter(todo => {
            return todo.id !== removeTodo.id
        })
        }
    }
}
</script>

<style scoped>
   .completed {
      color: gray;
      text-decoration-line: line-through;
    }
</style>