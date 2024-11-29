<script setup>
    const props = defineProps(['math'])
</script>

<template>
    <h2 class="my-4">=</h2>
    <p class="border border-dark rounded w-100 fs-2 d-flex align-items-center justify-content-center" style="height: 10vh;">{{ props.math }}</p>
</template>