<template>
    <div class="xl:px-[15em] lg:px-[5em] px-[1em] lg:h-[10svh] py-[0.5em] sticky z-50 flex justify-between items-center"
        :class="isScrolled ? 'bg-[#F8F8F8] top-0 shadow-lg transition-colors duration-300' : 'md:py-[3em] bg-[#73a942]'">
        <NuxtLink to="/" class="flex items-center hover:text-[#004b23]">
            <img src="~/assets/images/icon.png" alt="" :width="isScrolled ? 80 : 120" class="transition-all duration-300">
            <div :class='isScrolled ? "transition-opacity duration-300 px-[0.5em] opacity-100" : "opacity-0 w-0 overflow-hidden"'>
                <p class="text-[12pt] whitespace-nowrap">Clean Planet Eco Solution</p>
                <p class="text-[12pt] whitespace-nowrap">Private Ltd</p>
            </div>
        </NuxtLink>
        <div class="lg:hidden flex items-center">
            <button class="hover:fill-[#004b23] transition-colors duration-300" 
                :class="isScrolled ? 'text-[#000]' : 'text-[#f8f8f8]'"
                @click="isMenuOpen = true" aria-label="Open menu">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 -960 960 960" height="40px" width="40px"
                    fill="currentcolor">
                    <path d="M120-240v-80h720v80H120Zm0-200v-80h720v80H120Zm0-200v-80h720v80H120Z" />
                </svg>
            </button>
        </div>
        <div class="hidden lg:block">
            <nav class="hidden lg:flex gap-10 text-[13pt] text-black">
                <NuxtLink class="hover:text-[#004b23]" active-class="text-[#004b23] font-semibold" exact
                    to="/about">About</NuxtLink>
                <NuxtLink class="hover:text-[#004b23]" active-class="text-[#004b23] font-semibold" exact
                    to="/projects">Services</NuxtLink>
                <NuxtLink class="hover:text-[#004b23]" active-class="text-[#004b23] font-semibold" exact
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
let ticking = false

const handleScroll = () => {
    if (!ticking) {
        window.requestAnimationFrame(() => {
            isScrolled.value = window.scrollY > 50
            ticking = false
        })
        ticking = true
    }
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll, { passive: true })
    // Set initial state
    handleScroll()
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
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