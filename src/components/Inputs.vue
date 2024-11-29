<script setup>
    const props = defineProps(['x', 'y', 'symbol'])
</script>

<template>
    <div class="row mx-auto mt-4 w-100 justify-content-center">
        <div class="col-5" style="height: 6em;">
            <input @keyup="props.x" class="text-center h-100 w-100 fs-2 rounded" type="number" placeholder="x">
        </div>
        <div class="col-2" style="height: 6em;">
            <select @change="props.symbol" class="text-center h-100 w-100 fs-2 rounded">
                <option value="sum">+</option>
                <option value="subtract">-</option>
                <option value="divide">/</option>
                <option value="multiply">*</option>
            </select>
        </div>
        <div class="col-5" style="height: 6em;">
            <input @keyup="props.y" class="text-center h-100 w-100 fs-2 rounded" type="number" placeholder="y">
        </div>
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