<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import { router } from '@inertiajs/vue3'

const props = defineProps({
    title: String,
    mapsRoute: String,
    graphsRoute: String
})

const goToMaps = () => {
    router.visit(props.mapsRoute);
}

const goToGraphs = () => {
    router.visit(props.graphsRoute);
}
</script>

<template>
    <div class="flex flex-col items-center gap-4">
        <h1 class="text-2xl">{{ props.title }}</h1>

        <div class="flex flex-col w-fit justify-center gap-4">
            <PrimaryButton type="primary" v-on:click="goToMaps" class="custom-button">
                Mapas
            </PrimaryButton>

            <PrimaryButton type="primary" v-on:click="goToGraphs">
                Gráficos
            </PrimaryButton>
        </div>

    </div>
</template>

<style>
.custom-button {
    justify-content: center !important;
}
</style>