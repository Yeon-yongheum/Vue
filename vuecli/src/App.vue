<template>
    <div>
        <h1>Hm's Todo</h1>
        <TodoList category="취업"></TodoList>
        <TodoList category="수업"></TodoList>
        <TodoList category="개인"></TodoList>
    </div>
</template>
<script>
import TodoList from './components/TodoList.vue'
export default {
    components:{
        TodoList
    }
}
</script>

<style lang="">

</style>