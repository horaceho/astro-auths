<template>
    <nav>
        <div class="m-2">
            <nav class="flex" aria-label="Breadcrumb">
                <ol role="list" class="flex items-center space-x-2">
                    <li>
                        <div class="flex">
                            <a href="/" class="text-sm font-medium text-stone-500 hover:text-stone-700">
                                Home
                            </a>
                        </div>
                    </li>
                    <li v-if="$auth === 'member'">
                        <div class="flex items-center">
                            ．
                            <a href="/profile" class="ml-2 text-sm font-medium text-stone-500 hover:text-stone-700">
                                Profile
                            </a>
                        </div>
                    </li>
                    <li v-else="$auth === 'member'">
                        <div class="flex items-center">
                            ．
                            <a href="/login" class="ml-2 text-sm font-medium text-stone-500 hover:text-stone-700">
                                Login
                            </a>
                        </div>
                    </li>
                    <li>
                        <div class="flex items-center">
                            ．
                            <a href="/toggle" class="ml-2 text-sm font-medium text-stone-500 hover:text-stone-700">
                                Toggle ({{ $theme }})
                            </a>
                        </div>
                    </li>
                </ol>
            </nav>
        </div>
    </nav>
</template>

<script setup>
    import { useStore } from '@nanostores/vue';
    import { auth } from '../userStore.js';
    import { theme } from '../themeStore.js';

    // read the store value with the `useStore` hook
    const $auth = useStore(auth);
    const $theme = useStore(theme);
</script>
