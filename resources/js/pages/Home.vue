<script setup>
    import { ref } from 'vue'
    import AppLayout from '@/layouts/AppLayout.vue';
    import Hero from '@/components/Hero.vue';
    import GnaBadge from '@/components/GnaBadge.vue';
    import Select from '../components/Select.vue'
    import image1 from '../../images/image-1.jpg';
    import image2 from '../../images/image-2.jpg';

    const selectedFilter = ref(null)
</script>

<template>
    <AppLayout>
        <Hero />

        <!-- Intro Section -->
        <section class="py-16">
            <div class="mx-auto max-w-[1180px] px-4 sm:px-6 xxl:px-0">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl md:text-4xl lg:text-5xl">
                        GNA Hotel Solutions:
                    </h2>
                    <p class="mt-4 text-3xl md:text-4xl lg:text-5xl">
                        l'èxit online del teu hotel
                    </p>
                </div>

                <div class="mx-auto space-y-6">
                    <p class="text-justify leading-relaxed">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam  rhoncus, velit id viverra fermentum, mauris odio maximus augue, ac  pretium diam nunc non lacus. Suspendisse mattis pellentesque velit, a  vestibulum felis condimentum et. Aenean dapibus ante vitae dolor egestas aliquam. Ut maximus feugiat laoreet. Vestibulum maximus, neque vitae  mattis facilisis, nisi turpis sollicitudin orci, at mollis urna mi sit  amet nulla. Interdum et malesuada fames ac ante ipsum primis in  faucibus. Maecenas ornare pellentesque est tristique placerat.  Suspendisse velit elit, commodo sit amet libero at, mollis placerat  massa. Nunc elementum vulputate mauris vitae congue. Nunc vitae mi  ligula. Etiam viverra viverra ante, vel dictum nisl condimentum vitae.
                    </p>
                    <p class="text-justify leading-relaxed">
                        Pellentesque hendrerit sit amet mauris vel dapibus. In felis diam,  ornare vel iaculis et, egestas sit amet dolor. Nulla nec cursus dui.  Nulla vulputate dolor et nunc feugiat tempus. Nullam bibendum et dolor  quis ornare. Nam ac ante ac felis molestie dictum et et risus. Quisque  sagittis dignissim accumsan. Aliquam mattis volutpat condimentum.  Interdum et malesuada fames ac ante ipsum primis in faucibus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia  curae; Integer vel sem dolor. Fusce et massa feugiat, lacinia est sit  amet, consectetur orci.
                    </p>
                </div>
            </div>
        </section>

        <!-- Filter Section -->
        <section class="sticky top-[72px] z-40 bg-secondary py-8 shadow-md md:top-20">
            <div class="mx-auto max-w-[1180px] px-4 sm:px-6 xxl:px-0">
                <div class="flex flex-col gap-3 sm:flex-row sm:items-center sm:gap-6">
                    <span class="text-base sm:text-lg md:text-2xl">Filtrar per</span>
                    <div class="w-full max-w-xs">
                        <Select
                            v-model="selectedFilter"
                            :options="[
                                { id: 1, name: 'Item 1' },
                                { id: 2, name: 'Item 2' },
                                { id: 3, name: 'Item 3' }
                            ]"
                            placeholder="Seleccionar"
                        />
                    </div>
                </div>
            </div>
        </section>

         <!-- Articles Section -->
         <section class="bg-white py-16">
            <div class="mx-auto max-w-[1180px] px-4 sm:px-6 xxl:px-0">
                <div class="space-y-16">
                    <!-- Left -->
                    <article class="grid lg:grid-cols-[auto_1fr] items-center gap-8">
                        <div class="flex justify-start">
                            <img
                                :src="image2"
                                alt="Tecnología"
                                class="aspect-4/3 h-auto w-full max-w-md rounded-[25px] object-cover"
                            >
                        </div>
                        <div class="space-y-4">
                            <div>
                                <GnaBadge variant="primary">
                                    Tecnología
                                </GnaBadge>
                            </div>
                            <h3 class="text-2xl font-bold md:text-3xl">
                                Lorem ipsum
                            </h3>
                            <p class="leading-relaxed">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam  rhoncus, velit id viverra fermentum, mauris odio maximus augue, ac  pretium diam nunc non
                            </p>
                            <a href="#" class="inline-block text-primary underline transition-colors duration-200 hover:text-primary/75">
                                Més informació
                            </a>
                        </div>
                    </article>

                    <!-- Right -->
                    <article class="grid lg:grid-cols-[1fr_auto] items-center gap-8">
                        <div class="space-y-4 md:order-1">
                            <div class="flex flex-wrap gap-2">
                                <GnaBadge variant="primary">
                                    Màrqueting
                                </GnaBadge>
                                <GnaBadge variant="primary">
                                    Tecnología
                                </GnaBadge>
                            </div>
                            <h3 class="text-2xl font-bold md:text-3xl">
                                Lorem ipsum
                            </h3>
                            <p class="leading-relaxed">
                                Pellentesque hendrerit sit amet mauris vel dapibus. In felis diam,  ornare vel iaculis et, egestas sit amet dolor. Nulla nec cursus dui.  Nulla vulputate dolor et nunc feugiat tempus. Nullam bibendum et dolor  quis ornare. Nam ac ante ac felis molestie dictum et et risus. Quisque  sagittis dignissim accumsan. Aliquam mattis volutpat condimentum.  Interdum et malesuada fames ac ante ipsum primis in faucibus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia  curae; Integer vel sem dolor. Fusce et massa feugiat, lacinia est sit  amet, consectetur orci.Pellentesque hendrerit sit amet mauris vel dapibus. In felis diam,  ornare vel iaculis et, egestas sit amet dolor. Nulla nec cursus dui.  Nulla vulputate dolor et nunc feugiat tempus. Nullam bibendum et dolor  quis ornare. Nam ac ante ac felis molestie dictum et et risus. Quisque  sagittis dignissim accumsan. Aliquam mattis volutpat condimentum.  Interdum et malesuada fames ac ante ipsum primis in faucibus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia  curae; Integer vel sem dolor. Fusce et massa feugiat, lacinia est sit  amet, consectetur orci.
                            </p>
                            <a href="#" class="inline-block text-primary underline transition-colors duration-200 hover:text-primary/75">
                                Més informació
                            </a>
                        </div>
                        <div class="flex justify-start md:order-2 lg:justify-end">
                            <img
                                :src="image1"
                                alt="Màrqueting y Tecnología"
                                class="aspect-4/3 h-auto w-full max-w-md rounded-[25px] object-cover"
                            >
                        </div>
                    </article>
                </div>
            </div>
        </section>
    </AppLayout>
</template>
