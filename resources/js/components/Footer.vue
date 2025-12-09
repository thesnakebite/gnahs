<script setup>
    import { Link } from '@inertiajs/vue3';
    import logoDark from '../../images/logo-gnahs.png';
</script>

<template>
    <footer class="bg-secondary py-12">
        <div class="container mx-auto px-6">
            <div class="grid grid-cols-1 gap-8 lg:grid-cols-4">
                <!-- Logo -->
                <div class="lg:col-span-2">
                    <Link href="/" class="inline-block" view-transition>
                        <img
                            :src="logoDark"
                            alt="GNA Hotel Solutions"
                            class="h-10 w-auto max-w-full sm:h-12 md:h-14 lg:h-16"
                        >
                    </Link>
                </div>

                <div>
                    <ul class="flex flex-col gap-3">
                        <li>
                            <a
                                href="mailto:info@gnahs.com"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Contacte
                            </a>
                        </li>
                        <li>
                            <Link
                                href="#"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Newsletter
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="#"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Treballa amb nosaltres
                            </Link>
                        </li>
                    </ul>
                </div>

                <div>
                    <ul class="flex flex-col gap-3">
                        <li>
                            <Link
                                href="#"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Política de cookies
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="#"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Política de privacitat
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="#"
                                class="text-black text-base transition-colors duration-200 hover:text-primary"
                            >
                                Avís legal
                            </Link>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="mt-12 text-right">
                <p class="text-sm text-black">
                    Desenvolupat per
                    <a
                        href="https://www.gnahs.com"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="text-base font-semibold text-primary transition-colors duration-200 hover:text-primary/75"
                    >
                        GNA Hotel Solutions
                    </a>
                </p>
            </div>
        </div>
    </footer>
</template>
