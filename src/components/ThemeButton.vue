<template>
    <!--write to the imported store using `.set`-->
    <button @click="onClick" class="inline-flex items-center rounded border border-transparent bg-indigo-600 px-2.5 py-1.5 text-xs font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
        <div>{{ $theme }}</div>
    </button>
</template>

<script setup>
    import { useStore } from '@nanostores/vue';
    import { theme } from '../themeStore.js';

    // read the store value with the `useStore` hook
    const $theme = useStore(theme);

    function onClick() {
        theme.set($theme.value === 'light' ? 'dark' : 'light');
    }
</script>
