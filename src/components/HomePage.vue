<script setup>

import UILayout from './UILayout.vue';
import TopHeader from './TopHeader.vue';
import Resume from './resume/Index.vue'
import Movements from './Movements.vue'

</script>

<template>
    <UILayout>
        <template #header>
            <TopHeader />
        </template>
        <template #resume>
            <Resume />
        </template>
        <template #movements>
            <Movements />
        </template>
    </UILayout>
</template>