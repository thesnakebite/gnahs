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
        <div class="relative z-10 flex h-full items-end justify-center">
            <div class="mx-auto max-w-[1128px] px-4 pb-12 sm:px-6 sm:pb-16 md:pb-20 lg:pb-[116px] xxl:px-0">
                <h1 class="text-center text-4xl font-bold tracking-tight text-white sm:text-5xl md:text-6xl lg:text-7xl xxl:text-8xl">
                    GNA HOTEL SOLUTIONS
                </h1>
            </div>
        </div>
    </section>
</template>
