<template>
    <li>
        <span v-bind:class="{ done: todo.completed }">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed">
            <strong>{{ todo.id }}</strong>
            {{ todo.title }}

        </span>
        <button class="rm" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
    </li>


</template>

<script>
import { on } from "events";

export default {
    props: {
        todo: {
            type: Object,
            require: true

        }
    }
}
</script>
<style>
li {
    border: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
    text-align: center;
}

.rm {
    border: none;
    background-color: red;
    color: #fff;
    border-radius: 50%;
    font-weight: bold;
    width: 30px;
    height: 30px;
    text-align: center;
}

input {
    margin-right: 1rem;
}

.done {
    text-decoration: line-through;
}
</style>