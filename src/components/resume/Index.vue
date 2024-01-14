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

const currencyFormatter = new Intl.NumberFormat('es-ES', {
    style: 'currency',
    currency: 'eur'
})

const displayedAmount = computed(() =>
    props.amount ? props.amount : props.totalAmount
)

const amountCurrency = computed(() => `${currencyFormatter.format(displayedAmount.value)}`)

</script>

<template>
    <main>
        <p>{{ label }}</p>
        <h1>{{ amountCurrency }}</h1>
        <div class="chart">
            <slot name="chart" />
        </div>
        <div class="action">
            <slot name="action"></slot>
        </div>
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

.chart {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 48px 24px;
    box-sizing: border-box;
}
</style>