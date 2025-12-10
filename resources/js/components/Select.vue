<script setup>
    import { ref } from 'vue';
    import { Listbox, ListboxButton, ListboxOption, ListboxOptions } from '@headlessui/vue';

    const props = defineProps({
        options: {
            type: Array,
            default: () => [
                { id: 1, name: 'Item 1' },
                { id: 2, name: 'Item 2' },
                { id: 3, name: 'Item 3' }
            ]
        },
        modelValue: {
            type: Object,
            default: null
        },
        placeholder: {
            type: String,
            default: 'Seleccionar'
        }
    });

    const emit = defineEmits(['update:modelValue']);

    const selected = ref(props.modelValue || { id: 0, name: props.placeholder });

    const updateSelected = (value) => {
        selected.value = value
        emit('update:modelValue', value)
    };
</script>

<template>
    <Listbox
        as="div"
        :model-value="selected"
        @update:model-value="updateSelected"
    >
        <div class="relative">
            <ListboxButton class="relative w-full cursor-pointer rounded-full border border-gray-300 bg-white py-2 pr-10 pl-4 text-left text-base text-black transition-all duration-200 hover:border-gray-400 focus:border-gray-500 focus:outline-none focus:ring-2 focus:ring-gray-200 sm:py-2.5 sm:pl-6 sm:text-xl">
                <span class="block truncate">{{ selected.name }}</span>
                <span class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3 sm:pr-4">
                    <svg class="size-10 text-gray-500 sm:size-14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="0.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
                        <polyline points="6 9 12 15 18 9"></polyline>
                    </svg>
                </span>
            </ListboxButton>

            <transition
                leave-active-class="transition ease-in duration-100"
                leave-from-class="opacity-100"
                leave-to-class="opacity-0"
            >
                <ListboxOptions class="absolute z-10 mt-2 max-h-60 w-full overflow-auto rounded-2xl bg-white py-2 shadow-lg ring-1 ring-black/5 focus:outline-none">
                    <ListboxOption
                        v-for="option in options"
                        :key="option.id"
                        v-slot="{ active, selected }"
                        as="template"
                        :value="option"
                    >
                        <li
                            :class="[
                                active ? 'bg-primary/10 text-gray-900' : 'text-gray-700',
                                'relative cursor-pointer select-none py-3 pr-9 pl-6 transition-colors duration-150'
                            ]"
                        >
                            <span
                                :class="[
                                    selected ? 'font-semibold' : 'font-normal',
                                    'block truncate'
                                ]"
                            >
                                {{ option.name }}
                            </span>

                            <span
                                v-if="selected"
                                :class="[
                                    active ? 'text-primary' : 'text-primary',
                                    'absolute inset-y-0 right-0 flex items-center pr-4'
                                ]"
                            >
                                <svg class="size-5" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                                    <path fill-rule="evenodd" d="M16.704 4.153a.75.75 0 0 1 .143 1.052l-8 10.5a.75.75 0 0 1-1.127.075l-4.5-4.5a.75.75 0 0 1 1.06-1.06l3.894 3.893 7.48-9.817a.75.75 0 0 1 1.05-.143Z" clip-rule="evenodd" />
                                </svg>
                            </span>
                        </li>
                    </ListboxOption>
                </ListboxOptions>
            </transition>
        </div>
    </Listbox>
</template>
