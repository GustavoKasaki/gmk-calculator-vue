<script setup>
    import { reactive } from 'vue';
    import Header from './components/Header.vue';
    import Inputs from './components/Inputs.vue';
    import Result from './components/Result.vue';

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
        <Header />
        <Inputs :x="event => state.x = event.target.value" :y="event => state.y = event.target.value" :symbol="event => state.values = event.target.value"/>
        <Result :math="math()"/>
    </div>
</template>