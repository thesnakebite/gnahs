<script setup>
    defineProps({
        greeting: {
            type: String
        }
    })
</script>

<template>
    <div class="flex justify-center items-center h-dvh">
        <h1 class="text-amber-500 text-4xl">{{ greeting }}</h1>
    </div>
</template>
