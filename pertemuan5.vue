<script setup>
import { ref, computed } from 'vue'

const activity = ref("")
const todos = ref([
    { id: 1, text: "Mitsubishi Xpander", done: true },
    { id: 2, text: "Honda HR-V", done: false },
    { id: 3, text: "Honda Civic", done: false },
    { id: 4, text: "Suzuki Ertiga", done: false },
    { id: 5, text: "Toyota Veloz", done: false },
]);

const addData = () => {
    let data = {
        id: todos.value.length + 1,
        text: activity.value,
        done: false,
    };

    todos.value.push(data);
    activity.value = "";
};

const doneTodos = computed(() => {
    return todos.value.filter((todo) => todo.done === true);
});

const notDoneTodos = computed(() => {
    return todos.value.filter((todo) => todo.done === false);
});
</script>

<template>
    <h1>Pertemuan 5</h1>

    <input v-model="activity" />
    <button @click="addData">submit</button>

    <h1>Penjualan Mobil</h1>
    <ul>
        <li v-for="todo in todos" :key="todo.id">
            {{ todo.id }}. {{ todo.text }} - {{ todo.done }}
            <input type="checkbox" v-model="todo.done" />
        </li>
    </ul>

    <h1>Sudah Terjual</h1>
    <ul>
        <li v-for="todo in doneTodos" :key="todo.id">
            {{ todo.id }}. {{ todo.text }} - {{ todo.done }}
            <input type="checkbox" v-model="todo.done" />
        </li>
    </ul>

    <h1>Belum Terjual</h1>
    <ul>
        <li v-for="todo in notDoneTodos" :key="todo.id">
            {{ todo.id }}. {{ todo.text }} - {{ todo.done }}
            <input type="checkbox" v-model="todo.done" />
        </li>
    </ul>
</template>

<style>
/*tamabahkan css sesuai keinginan anda*/
</style>