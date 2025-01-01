<template>
    <a class="scroll-up" :class="{ 'visible': showScrollButton }" href="#" @click.prevent="scrollToTop"
        :aria-hidden="!showScrollButton" ref="scrollUpButton">
        <font-awesome-icon :icon="['fas', 'arrow-up']" />
    </a>
</template>

<script>
import { computed, ref, onMounted, onBeforeUnmount } from 'vue';

export default {
    setup() {
        const showScrollButton = computed(() => progress.value > startAnimation);
        const scrollUpButton = ref(null);
        const progress = ref(0);
        const startAnimation = 50;
        const endAnimation = 70;

        // Hooks
        function lerp(a, b, t) {
            t = Math.max(0, Math.min(1, t));
            return a + (b - a) * t;
        }

        function mapRange(value, start, end) {
            value = Math.max(start, Math.min(value, end));
            return (value - start) / (end - start);
        }

        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: "smooth",
            });
        }

        function updateProgress() {
            const scrollTop = window.scrollY;
            const scrollHeight = document.documentElement.scrollHeight;
            const clientHeight = document.documentElement.clientHeight;

            progress.value = (scrollTop / (scrollHeight - clientHeight)) * 100;

            if (!scrollUpButton.value) return;

            const mappedValue = lerp(0, 1, mapRange(progress.value, startAnimation, endAnimation));
            scrollUpButton.value.style.visibility = showScrollButton ? "visible" : "hidden";
            scrollUpButton.value.style.opacity = mappedValue;
            scrollUpButton.value.style.transform = `translateY(${mappedValue}rem)`;
        }

        onMounted(() => {
            window.addEventListener("scroll", updateProgress);
        });

        onBeforeUnmount(() => {
            window.removeEventListener("scroll", updateProgress);
        });

        return {
            scrollToTop,
            showScrollButton,
            scrollUpButton
        }
    },
}
</script>

<style>
.scroll-up {
    position: fixed;
    right: 2rem;
    bottom: 2rem;
    background-color: var(--surface-container);
    color: var(--on-surface);
    border-radius: 50%;
    text-align: center;
    z-index: 2;
    visibility: hidden;
    opacity: 0;
    transform: translateY(1rem);
    transition: transform 0.4s ease, opacity 0.4s ease, visibility 0.4s ease, background-color 0.4s ease;
    box-shadow: 0 2px 3px rgba(0, 0, 0, 0.3);
    text-shadow: 0 1px rgba(0, 0, 0, .3);
    width: 3rem;
    height: 3rem;
    line-height: 3rem;
    font-size: 1rem;
}

.scroll-up:hover {
    background-color: var(--surface-container-highest);
    cursor: pointer;
}

.scroll-up.visible {
    visibility: visible;
    opacity: 1;
    transform: translateY(0);
}

@media (min-width: 48rem) {
    .scroll-up {
        width: 4rem;
        height: 4rem;
        line-height: 4rem;
        font-size: 2rem;
    }
}
</style>
