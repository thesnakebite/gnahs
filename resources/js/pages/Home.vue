<script setup>
    import AppLayout from '../layouts/AppLayout.vue';
    import Hero from '@/components/Hero.vue';

    defineProps({
        greeting: {
            type: String
        }
    })
</script>

<template>
    <AppLayout>
        <Hero />

        <!-- Intro Section -->
        <section class="bg-gray-50 py-16">
            <div class="container mx-auto px-6">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl md:text-4xl lg:text-5xl">
                        GNA Hotel Solutions:
                    </h2>
                    <p class="mt-4 text-3xl md:text-4xl lg:text-5xl">
                        l'èxit online del teu hotel
                    </p>
                </div>

                <div class="mx-auto max-w-5xl space-y-6">
                    <p class="text-justify leading-relaxed">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam rhoncus, velit id viverra fermentum, mauris odio maximus augue, ac pretium diam nunc non lacus. Suspendisse mattis pellentesque velit, a vestibulum felis condimentum et. Aenean dapibus ante vitae dolor egestas aliquam. Ut maximus feugiat lacus. Vestibulum maximus, neque vitae mattis facilisis, nisl turpis sollicitudin orci, at mollis urna mi sit amet nulla. Interdum et malesuada fames ac ante ipsum primis in faucibus. Maecenas ornare pellentesque est tristique placerat. Suspendisse velit elit, commodo sit amet libero at, mollis placerat massa. Nunc elementum vulputate mauris vitae congue. Nunc vitae mi ligula. Etiam viverra viverra ante, vel dictum nisl condimentum vitae.
                    </p>
                    <p class="text-justify leading-relaxed">
                        Pellentesque hendrerit sit amet mauris vel dapibus. In felis diam, ornare vel iaculis et, egestas sit amet dolor. Nulla nec cursus dui. Nulla vulputate dolor et nunc feugiat tempus. Nullam bibendum et dolor quis ornare. Nam ac ante ac felis molestie dictum et et risus. Quisque sagittis dignissim accumsan. Aliquam mattis volutpat condimentum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Integer vel sem dolor. Fusce et massa feugiat, lacinia est sit amet, consectetur orci.
                    </p>
                </div>
            </div>
        </section>
    </AppLayout>
</template>
