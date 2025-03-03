<template>
    <header class="flex flex-row w-full bg-rose-50 border-b-2 border-rose-500 items-center justify-between px-4 py-2 gap-4 relative">
        <div class="basis-1/4 items-center justify-start px-8 min-w-40 max-sm:basis-auto">
            <img src="assets/images/flower.png" class="w-20 h-20 bg-transparent">
        </div>
        <div class="basis-1/4 max-sm:basis-auto"></div>

        <nav class="basis-1/2 flex flex-row items-center justify-end px-8 gap-4 max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-white">
            <NuxtLink to="/" class="my-auto p-2 hover:bg-pink-200 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center">Home</NuxtLink>
            
            <!-- Dropdown for Labs -->
            <div class="relative">
                <button class="p-2 hover:bg-pink-200 hover:text-white max-sm:w-full" @click="switch_submenu">Labs</button>
                <div v-show="submenu" class="absolute top-full left-0 bg-white text-black shadow-md w-56 text-center max-sm:w-full max-sm:bg-red-100">
                    <NuxtLink to="/lab1" class="block p-2 border-b hover:bg-gray-500 hover:text-white max-sm:text-center">Lab1</NuxtLink>
                    <NuxtLink to="/lab2" class="block p-2 border-b hover:bg-gray-500 hover:text-white max-sm:text-center">Lab2</NuxtLink>
                    <NuxtLink to="/lab3" class="block p-2 border-b hover:bg-gray-500 hover:text-white max-sm:text-center">Lab3</NuxtLink>
                    <NuxtLink to="/lab4" class="block p-2 border-b hover:bg-gray-500 hover:text-white max-sm:text-center">Lab4</NuxtLink>
                    <NuxtLink to="/lab5" class="block p-2 border-b hover:bg-gray-500 hover:text-white max-sm:text-center">Lab5</NuxtLink>
                    <NuxtLink to="/lab6" class="block p-2 hover:bg-gray-500 hover:text-white max-sm:text-center">Lab6</NuxtLink>
                </div>
            </div>

            <NuxtLink to="/login" class="p-2 hover:bg-pink-200 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center">Login</NuxtLink>
            <NuxtLink to="/logout" class="p-2 hover:bg-pink-200 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center">Logout</NuxtLink>
        </nav>

        <!-- Burger Menu -->
        <div v-if="!burger" @click="switch_burger" class="max-sm:flex max-sm:flex-col max-sm:m-8 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6">
            <span class="h-[3px] w-full bg-black"></span>
            <span class="h-[3px] w-full bg-black"></span>
            <span class="h-[3px] w-full bg-black"></span>
        </div>
        <div v-else class="max-sm:flex max-sm:flex-col max-sm:m-8 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6" @click="switch_burger">
            <span class="h-[3px] w-full bg-blue-950"></span>
            <span class="h-[3px] w-full bg-blue-950 opacity-50"></span>
            <span class="h-[3px] w-full bg-blue-950 relative bottom-3 rotate-[45deg]"></span>
        </div>
    </header>

    <main class="p-5 flex h-screen">
        <slot />
    </main>

    <footer class="flex flex-row w-full bg-rose-50 border-t-2 border-rose-500 items-center justify-center px-4 py-2 gap-4">
        <a href="https://www.instagram.com/abntrld">
            <img src="assets/images/inst.png" class="w-16 h-16">
        </a>
    </footer>
</template>

<script>
export default {
    data() {
        return {
            burger: false,
            submenu: false
        };
    },
    methods: {
        switch_burger() {
            this.burger = !this.burger;
        },
        switch_submenu() {
            this.submenu = !this.submenu;
        }
    }
};
</script>
