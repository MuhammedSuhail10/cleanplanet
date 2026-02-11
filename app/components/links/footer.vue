<script setup>
const now = new Date();
const currentYear = now.getFullYear();
</script>

<template>
    <div class="xl:px-[15em] lg:px-[5em] px-[1em] md:py-[5em] py-[2em] pb-[2em] bg-[#C7C4B7]/50">
        <div class="flex flex-col md:flex-row gap-[1em] justify-between">
            <NuxtLink to="/" class="flex flex-col items-center justify-center hover:text-[#004b23]">
                <img src="~/assets/images/icon.avif" alt="" width="120" class="transition-all duration-300">
                <div class='transition-opacity duration-300 px-[0.5em] opacity-100 text-center'>
                    <p class="text-[15pt] whitespace-nowrap">Clean Planet Eco Solution</p>
                    <p class="text-[15pt] whitespace-nowrap">Private Ltd</p>
                </div>
            </NuxtLink>
            <div>
                <h5 class="font-[sansita] text-[#004b23] text-[20pt] text-center">Navigation</h5>
                <div class="flex flex-col gap-[0.5em] my-[1em] text-center text-[15pt]">
                    <NuxtLink class="hover:text-[#004b23]" exact to="/">
                        Home</NuxtLink>
                    <NuxtLink class="hover:text-[#004b23]" exact to="/about">
                        About</NuxtLink>
                    <NuxtLink class="hover:text-[#004b23]" exact to="/services">
                        Services</NuxtLink>
                    <NuxtLink class="hover:text-[#004b23]" exact to="/contact">
                        Contact</NuxtLink>
                </div>
            </div>
            <div>
                <h5 class="font-[sansita] text-[#004b23] text-[20pt] text-center md:text-start">Contact Us</h5>
                <div class="flex flex-col gap-[0.5em] items-center md:items-start my-[1em] text-[15pt]">
                    <div class="flex gap-[0.5em] items-start">
                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none">
                            <path
                                d="M20.621 8.45c-1.05-4.62-5.08-6.7-8.62-6.7h-.01c-3.53 0-7.57 2.07-8.62 6.69-1.17 5.16 1.99 9.53 4.85 12.28a5.436 5.436 0 0 0 3.78 1.53c1.36 0 2.72-.51 3.77-1.53 2.86-2.75 6.02-7.11 4.85-12.27Zm-8.62 5.01a3.15 3.15 0 1 1 0-6.3 3.15 3.15 0 0 1 0 6.3Z"
                                fill="#000"></path>
                        </svg>
                        <p class="cursor-pointer hover:text-[#004b23] text-center md:text-start">Clean Planet Recycle Pvt Ltd, Kunnathunad, <br /> Arackapady, Ernakulam</p>
                    </div>
                    <div class="flex gap-[0.5em] items-start">
                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none">
                            <path fill="#000"
                                d="M11.05 14.95L9.2 16.8c-.39.39-1.01.39-1.41.01-.11-.11-.22-.21-.33-.32a28.414 28.414 0 01-2.79-3.27c-.82-1.14-1.48-2.28-1.96-3.41C2.24 8.67 2 7.58 2 6.54c0-.68.12-1.33.36-1.93.24-.61.62-1.17 1.15-1.67C4.15 2.31 4.85 2 5.59 2c.28 0 .56.06.81.18.26.12.49.3.67.56l2.32 3.27c.18.25.31.48.4.7.09.21.14.42.14.61 0 .24-.07.48-.21.71-.13.23-.32.47-.56.71l-.76.79c-.11.11-.16.24-.16.4 0 .08.01.15.03.23.03.08.06.14.08.2.18.33.49.76.93 1.28.45.52.93 1.05 1.45 1.58.1.1.21.2.31.3.4.39.41 1.03.01 1.43zM21.97 18.33a2.54 2.54 0 01-.25 1.09c-.17.36-.39.7-.68 1.02-.49.54-1.03.93-1.64 1.18-.01 0-.02.01-.03.01-.59.24-1.23.37-1.92.37-1.02 0-2.11-.24-3.26-.73s-2.3-1.15-3.44-1.98c-.39-.29-.78-.58-1.15-.89l3.27-3.27c.28.21.53.37.74.48.05.02.11.05.18.08.08.03.16.04.25.04.17 0 .3-.06.41-.17l.76-.75c.25-.25.49-.44.72-.56.23-.14.46-.21.71-.21.19 0 .39.04.61.13.22.09.45.22.7.39l3.31 2.35c.26.18.44.39.55.64.1.25.16.5.16.78z">
                            </path>
                        </svg>
                        <a href="tel:+917012031396" class="hover:text-[#004b23]">+91 70120 31396</a>
                    </div>
                    <div class="flex gap-[0.5em] items-start">
                        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none">
                            <path
                                d="M16 2H8C4 2 2 4 2 8v13c0 .55.45 1 1 1h13c4 0 6-2 6-6V8c0-4-2-6-6-6Zm-2 13.25H7c-.41 0-.75-.34-.75-.75s.34-.75.75-.75h7c.41 0 .75.34.75.75s-.34.75-.75.75Zm3-5H7c-.41 0-.75-.34-.75-.75s.34-.75.75-.75h10c.41 0 .75.34.75.75s-.34.75-.75.75Z"
                                fill="#000"></path>
                        </svg>
                        <a href="mailto:cleanplanetfrk@gmail.com" class="hover:text-[#004b23]">cleanplanetfrk@gmail.com</a>
                    </div>
                </div>
            </div>
        </div>

        <div class="mt-[2em]">
            <hr />
            <div class="flex mt-[1em]">
                <p>Copyright ©{{ currentYear }}. All Rights Reserved By <a href="/"
                        class="text-[#004b23] font-semibold">Clean Planet Eco Solution</a></p>
            </div>
        </div>
    </div>
</template>