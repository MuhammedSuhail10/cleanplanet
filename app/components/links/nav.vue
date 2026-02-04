<template>
    <div class="xl:px-[12em] lg:px-[5em] px-[1em] h-[10svh] sticky z-50  flex justify-between items-center"
        :class="isScrolled ? 'bg-[#F8F8F8] top-0 shadow-sm transition-colors duration-300' : 'top-2'">
        <NuxtLink to="/" class="flex items-center hover:text-[#004b23]">
            <img src="~/assets/images/icon.png" alt="" :width="isScrolled ? 80 : 120">
            <div :class='isScrolled ? "transition-text duration-300 px-[0.5em]" : "hidden"'>
                <p class="text-[12pt]">Clean Planet Eco Solution</p>
                <p class="text-[12pt]">Private Ltd</p>
            </div>
        </NuxtLink>
        <div class="lg:hidden flex items-center">
            <button class="hover:fill-[#004b23]" :class="isScrolled ? 'text-[#000]' : 'text-[#f8f8f8]'"
                @click="isMenuOpen = true" aria-label="Open menu">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 -960 960 960" height="25px" width="25px"
                    fill="currentcolor">
                    <path d="M120-240v-80h720v80H120Zm0-200v-80h720v80H120Zm0-200v-80h720v80H120Z" />
                </svg>
            </button>
        </div>
        <div class="hidden lg:block">
            <nav class="hidden lg:flex gap-10 text-[13pt] "
                :class="isScrolled ? 'text-black/60 ' : 'text-white/60'">
                <NuxtLink class="hover:text-[#004b23] " active-class="text-[#004b23] font-semibold" exact
                    to="/about">About</NuxtLink>
                <NuxtLink class="hover:text-[#004b23] " active-class="text-[#004b23] font-semibold" exact
                    to="/projects">Services</NuxtLink>
                <NuxtLink class="hover:text-[#004b23] " active-class="text-[#004b23] font-semibold" exact
                    to="/contact">Contact</NuxtLink>
            </nav>
        </div>
    </div>

    <ClientOnly>
        <HelpersDrawer v-if="isMenuOpen" class="bg-[#F0F8FF]" :is-menu-open="isMenuOpen"
            @close="isMenuOpen = false" />
    </ClientOnly>
</template>

<script setup>
import { ref, onMounted, onUnmounted, watch } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
    isScrolled.value = window.scrollY > 50
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
    // Cleanup: ensure scroll is restored
    document.body.style.overflow = ''
})

const route = useRoute()
const isMenuOpen = ref(false)

// Close drawer on route change
watch(
    () => route.path,
    () => {
        isMenuOpen.value = false
    }
)

// Lock/unlock body scroll when drawer opens/closes
watch(isMenuOpen, (newValue) => {
    if (newValue) {
        document.body.style.overflow = 'hidden'
    } else {
        document.body.style.overflow = ''
    }
})
</script>