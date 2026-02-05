<script setup>
const now = new Date();
const currentYear = now.getFullYear();
</script>

<template>
    <div class="xl:px-[15em] lg:px-[5em] px-[1em] md:py-[5em] py-[2em] pb-[2em] bg-[#C7C4B7]/50">
        <div class="flex flex-col md:flex-row gap-[1em] justify-between">
            <NuxtLink to="/" class="flex flex-col items-center justify-center hover:text-[#004b23]">
                <img src="~/assets/images/icon.png" alt="" width="120"
                    class="transition-all duration-300">
                <div class='transition-opacity duration-300 px-[0.5em] opacity-100 text-center'>
                    <p class="text-[15pt] whitespace-nowrap">Clean Planet Eco Solution</p>
                    <p class="text-[15pt] whitespace-nowrap">Private Ltd</p>
                </div>
            </NuxtLink>
            <div>
                <h5 class="font-[sansita] text-[#004b23] text-[20pt] text-center">Navigation</h5>
                <div class="flex flex-col gap-[0.5em] my-[1em] text-center text-[15pt]">
                    <p>Home</p>
                    <p>About</p>
                    <p>Services</p>
                    <p>Contact</p>
                </div>
            </div>
            <div>
                <h5 class="font-[sansita] text-[#004b23] text-[20pt] text-center">Contact Us</h5>
            </div>
        </div>

        <div class="mt-[2em]">
            <hr />
            <div class="flex mt-[1em]">
                <p>Copyright ©{{ currentYear }}. All Rights Reserved By <a href="/" class="text-[#004b23] font-semibold">Clean Planet Eco Solution</a></p>
            </div>
        </div>
    </div>
</template>