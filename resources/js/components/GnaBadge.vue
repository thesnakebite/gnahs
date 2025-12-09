<script setup>
    defineProps({
        variant: {
            type: String,
            default: 'primary',
            validator: (value) => ['primary', 'secondary'].includes(value)
        }
    })

    const variantClasses = {
        primary: 'bg-primary text-white',
        secondary: 'bg-secondary'
    }
</script>

<template>
    <span
        :class="[
            variantClasses[variant],
            'inline-block rounded-[25px] px-4 py-2 text-base'
        ]"
    >
        <slot />
    </span>
</template>
