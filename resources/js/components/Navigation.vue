<script setup>
    import { Link } from '@inertiajs/vue3';
    import { ref, onMounted, onUnmounted } from 'vue';
    import logoWhite from '../../images/logo-gnahs-white.png';
    import logoFullWhite from '../../images/logo-gnahs-full-white.png';
    import logoDark from '../../images/logo-gnahs.png';

    const mobileMenuOpen = ref(false);
    const isScrolled = ref(false);

    const toggleMobileMenu = () => {
        mobileMenuOpen.value = !mobileMenuOpen.value
    };

    const closeMobileMenu = () => {
        mobileMenuOpen.value = false
    };

    const handleScroll = () => {
        isScrolled.value = window.scrollY > 50
    };

    onMounted(() => {
        window.addEventListener('scroll', handleScroll)
    });

    onUnmounted(() => {
        window.removeEventListener('scroll', handleScroll)
    });
</script>

<template>
    <header
        :class="[
            'fixed left-0 right-0 top-0 z-50 transition-all duration-300',
            isScrolled ? 'bg-primary shadow-lg' : 'bg-transparent'
        ]"
    >
        <div
            :class="[
                'container mx-auto px-6 transition-all duration-300',
                isScrolled ? 'py-4' : 'py-12'
            ]"
        >
            <div class="flex items-center justify-between">
                <!-- Logo -->
                <Link href="/" class="flex" view-transition>
                    <img
                        :src="isScrolled ? logoFullWhite : logoWhite"
                        alt="GNA Hotel Solutions"
                        class="h-10 w-60 transition-all duration-300 md:h-12 md:w-72 lg:h-14 lg:w-80"
                    >
                </Link>

                <!-- Desktop Navigation -->
                <nav class="hidden lg:block">
                    <ul class="flex items-center gap-8">
                        <li>
                            <Link
                                href="#"
                                class="text-white text-lg transition-colors duration-200 hover:text-white/80"
                            >
                                Hotel
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="#"
                                class="text-white text-lg transition-colors duration-200 hover:text-white/80"
                            >
                                Ofertas
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="#"
                                as="button"
                                class="inline-block cursor-pointer rounded-full border border-white px-4 py-1.5 text-sm font-medium text-white transition-all duration-200 hover:bg-white hover:text-gray-900 md:text-base lg:text-lg"
                            >
                                Reservar
                            </Link>
                        </li>
                    </ul>
                </nav>

                <!-- Mobile Hamburger Button -->
                <button
                    @click="toggleMobileMenu"
                    class="relative z-50 flex h-10 w-10 flex-col items-center justify-center gap-1.5 lg:hidden"
                    aria-label="Toggle menu"
                >
                    <span
                        :class="[
                            mobileMenuOpen ? 'translate-y-2 rotate-45 bg-gray-800 sm:bg-white' : 'bg-white'
                        ]"
                        class="block h-0.5 w-6 transition-all duration-300"
                    >
                    </span>
                    <span
                        :class="[
                            mobileMenuOpen ? 'opacity-0' : 'opacity-100',
                            'bg-white'
                        ]"
                        class="block h-0.5 w-6 transition-all duration-300"
                    >
                    </span>
                    <span
                        :class="[
                            mobileMenuOpen ? '-translate-y-2 -rotate-45 bg-gray-800 sm:bg-white' : 'bg-white'
                        ]"
                        class="block h-0.5 w-6 transition-all duration-300"
                    >
                    </span>
                </button>
            </div>

            <!-- Backdrop -->
            <Transition
                enter-active-class="transition-opacity duration-300 ease-out"
                enter-from-class="opacity-0"
                enter-to-class="opacity-100"
                leave-active-class="transition-opacity duration-200 ease-in"
                leave-from-class="opacity-100"
                leave-to-class="opacity-0"
            >
                <div
                    v-if="mobileMenuOpen"
                    @click="closeMobileMenu"
                    class="fixed inset-0 z-40 bg-black/50 backdrop-blur-sm lg:hidden"
                >
                </div>
            </Transition>

            <!-- Side Drawer -->
            <Transition
                enter-active-class="transition-transform duration-300 ease-out"
                enter-from-class="-translate-x-full"
                enter-to-class="translate-x-0"
                leave-active-class="transition-transform duration-200 ease-in"
                leave-from-class="translate-x-0"
                leave-to-class="-translate-x-full"
            >
                <!-- Desktop Mobile -->
                <nav
                    v-if="mobileMenuOpen"
                    class="fixed left-0 top-0 z-40 h-full w-full bg-white shadow-xl sm:w-72 lg:hidden"
                >
                    <div class="flex h-full flex-col px-6 py-8">
                        <!-- Logo in Drawer -->
                        <div class="mb-8">
                            <Link href="/" @click="closeMobileMenu" class="block">
                                <img
                                    :src="logoDark"
                                    alt="GNA Hotel Solutions"
                                    class="h-10 w-auto"
                                >
                            </Link>
                        </div>

                        <ul class="flex flex-col gap-2">
                            <li>
                                <Link
                                    href="#"
                                    @click="closeMobileMenu"
                                    class="block py-4 text-lg text-gray-800 transition-colors duration-200 hover:text-gray-600"
                                >
                                    Hotel
                                </Link>
                            </li>
                            <li>
                                <Link
                                    href="#"
                                    @click="closeMobileMenu"
                                    class="block py-4 text-lg text-gray-800 transition-colors duration-200 hover:text-gray-600"
                                >
                                    Ofertas
                                </Link>
                            </li>
                            <li>
                                <Link
                                    href="#"
                                    @click="closeMobileMenu"
                                    class="mt-4 block cursor-pointer rounded-full border-2 border-gray-800 px-6 py-3 text-center text-sm font-medium text-gray-800 transition-all duration-200 hover:bg-gray-800 hover:text-white md:text-base lg:text-lg"
                                >
                                    Reservar
                                </Link>
                            </li>
                        </ul>
                    </div>
                </nav>
            </Transition>
        </div>
    </header>
</template>
