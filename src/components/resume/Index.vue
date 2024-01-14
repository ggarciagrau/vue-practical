<script setup>

import { computed } from 'vue';

const props = defineProps({
    label: String,
    totalAmount: Number,
    amount: {
        type: Number,
        required: false
    }
})

const displayedAmount = computed(() =>
    props.amount ? props.amount : props.totalAmount
)


</script>

<template>
    <main>
        <p>{{ label }}</p>
        <h1>{{ displayedAmount }}</h1>
    </main>
</template>

<style scoped>
main {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
}

h1,
p {
    margin: 0;
    text-align: center;
}

h1 {
    margin-top: 14px;
    color: var(--brand-green);
}

.graphic {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 48px 24px;
    box-sizing: border-box;
}
</style>