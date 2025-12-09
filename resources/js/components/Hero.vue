<script setup>
    import heroImage from '../../images/girona.jpg';
</script>

<template>
    <section class="relative h-[500px] w-full overflow-hidden sm:h-[600px] md:h-[700px] lg:h-[818px] xl:h-[960px] 2xl:h-dvh">
        <!-- Background Image -->
        <img
            :src="heroImage"
            alt="Girona cityscape"
            class="absolute inset-0 h-full w-full object-cover object-center"
        >

        <!-- Overlay -->
        <div class="absolute inset-0 bg-black/20"></div>

        <!-- Hero Content -->
        <div class="relative z-10 flex h-full items-end justify-center px-6 pb-12 sm:pb-16 md:px-8 md:pb-20 lg:px-12 lg:pb-[116px]">
            <h1 class="text-center text-4xl font-bold tracking-wider text-white sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl">
                GNA HOTEL SOLUTIONS
            </h1>
        </div>
    </section>
</template>
