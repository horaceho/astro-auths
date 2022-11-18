<template>
    <!--write to the imported store using `.set`-->
    <button @click="onClick" class="inline-flex items-center rounded border border-transparent bg-indigo-600 px-2.5 py-1.5 text-xs font-medium text-white shadow-sm hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
        <div>{{ $auth }}</div>
    </button>
</template>

<script setup>
    import { useStore } from '@nanostores/vue';
    import { auth } from '../userStore.js';

    // read the store value with the `useStore` hook
    const $auth = useStore(auth);

    function onClick() {
        auth.set($auth.value === 'member' ? 'guest' : 'member');
    }
</script>
