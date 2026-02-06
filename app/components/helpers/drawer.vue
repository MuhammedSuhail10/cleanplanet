<template>
    <div class="menu-dialog " :class="{ 'open': isMenuOpen }" @click.self="$emit('close')">
        <div class="menu-content ">
            <button class="close-button" @click="$emit('close')" aria-label="Close menu">
                <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960" width="24px"
                    fill="currentcolor">
                    <path
                        d="m256-200-56-56 224-224-224-224 56-56 224 224 224-224 56 56-224 224 224 224-56 56-224-224-224 224Z" />
                </svg>
            </button>
            <nav class="mobile-nav">
                <NuxtLink class="hover:text-[#004b23] text-[1.5em]" active-class="text-[#004b23] font-bold" exact
                    to="/" @click="$emit('close')">Home</NuxtLink>
                <NuxtLink class="hover:text-[#004b23] text-[1.5em]" active-class="text-[#004b23] font-bold" exact
                    to="/about" @click="$emit('close')">About</NuxtLink>
                <NuxtLink class="hover:text-[#004b23] text-[1.5em]" active-class="text-[#004b23] font-bold" exact
                    to="/services" @click="$emit('close')">Services</NuxtLink>
                <NuxtLink class="hover:text-[#004b23] text-[1.5em]" active-class="text-[#004b23] font-bold" exact
                    to="/contact" @click="$emit('close')">Contact</NuxtLink>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        isMenuOpen: {
            type: Boolean,
            required: true
        }
    },
    emits: ['close']
}
</script>

<style scoped>
.menu-dialog {
    width: 80%;
    height: 100dvh;
    position: fixed;
    top: 0;
    left: 1;
    right: 0;
    bottom: 0;
    display: flex;
    justify-content: flex-end;
    align-items: stretch;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease, visibility 0.3s ease;
    z-index: 1000;
}

.menu-dialog.open {
    opacity: 1;
    visibility: visible;
}

.menu-content {
    width: 100%;
    height: 100dvh;
    /* max-width: 400px; */
    padding: 5em;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-evenly;
    gap: 1.5em;
    position: relative;
    transform: translateX(100%);
    transition: transform 0.3s ease;
}

.menu-dialog.open .menu-content {
    transform: translateX(0);
}

.close-button {
    position: absolute;
    top: 1em;
    right: 1em;
    background: transparent;
    border: none;
    cursor: pointer;
    padding: 0.5em;
}

.mobile-nav {
    display: flex;
    flex-direction: column;
    gap: 1em;
    text-align: center;
    /* margin-top: 3em; */
}

.mobile-nav a {
    text-decoration: none;
    padding: 0.5em;
    transition: color 0.2s ease;
}
</style>