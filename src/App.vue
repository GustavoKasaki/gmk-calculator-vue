<script setup>
    import { reactive } from 'vue';

    const state = reactive ({
        values: 'sum',
        x: 0,
        y: 0,
        result: 0,
    })

    const math = () => {
        const {values} = state;

        switch (values) {
            case 'sum':
                return Number(state.x) + Number(state.y);
            case 'subtract':
                return Number(state.x) - Number(state.y);
            case 'divide':
                return Number(state.y) !== 0 ? (Number(state.x) / Number(state.y)) : 'Division by zero is not possible!';
            case 'multiply':
                return Number(state.x) * Number(state.y);
            default:
                return 'Invalid operation'
        }
    }
</script>

<template>
    <div class="container mx-auto my-5 text-center">
        <header class="my-3">
            <h1 class="bg-info p-2 border border-primary rounded">Arithmetic calculator</h1>
        </header>
        <div class="row mx-auto mt-4 w-100 justify-content-center">
            <div class="col-5" style="height: 6em;">
                <input @keyup="event => state.x = event.target.value" class="text-center h-100 w-100 fs-2 rounded" type="number" placeholder="x">
            </div>
            <div class="col-2" style="height: 6em;">
                <select @change="event => state.values = event.target.value" class="text-center h-100 w-100 fs-2 rounded">
                    <option value="sum">+</option>
                    <option value="subtract">-</option>
                    <option value="divide">/</option>
                    <option value="multiply">*</option>
                </select>
            </div>
            <div class="col-5" style="height: 6em;">
                <input @keyup="event => state.y = event.target.value" class="text-center h-100 w-100 fs-2 rounded" type="number" placeholder="y">
            </div>
        </div>
        <h2 class="my-4">=</h2>
        <p class="border border-dark rounded w-100 fs-2 d-flex align-items-center justify-content-center" style="height: 10vh;">{{ math() }}</p>
    </div>
</template>

<style scoped>
/* Remove arrows from number input fields */
/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
/* Firefox */
input[type=number] {
    -moz-appearance: textfield;
}
</style>
