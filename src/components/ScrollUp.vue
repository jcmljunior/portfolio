<template>
    <a class="scroll-up" :class="{ 'visible': showScrollButton }" href="#" @click.prevent="scrollToTop"
        :aria-hidden="!showScrollButton" ref="scrollUpButton">
        <font-awesome-icon :icon="['fas', 'arrow-up']" />
    </a>
</template>

<script>
export default {
    computed: {
        showScrollButton() {
            return this.progress > 60;
        }
    },
    data() {
        return {
            showScrollButton: false,
            interpolation: 0,
            progress: 0,
        };
    },
    methods: {
        updateProgress() {
            const scrollTop = window.scrollY;
            const scrollHeight = document.documentElement.scrollHeight;
            const clientHeight = document.documentElement.clientHeight;
            const startAnimation = 50;
            const endAnimation = 70;

            this.interpolation = scrollTop / (scrollHeight - clientHeight);
            this.progress = this.interpolation * 100;

            const mappedValue = this.lerp(0, 1, this.mapRange(this.progress, startAnimation, endAnimation));

            this.$refs.scrollUpButton.style.visibility = this.progress > startAnimation ? "visible" : "hidden";
            this.$refs.scrollUpButton.style.opacity = this.lerp(0, 1, mappedValue);
            this.$refs.scrollUpButton.style.transform = `translateY(${this.lerp(0, 1, mappedValue)}rem)`;
        },

        lerp(a, b, t) {
            t = Math.max(0, Math.min(1, t));
            return a + (b - a) * t;
        },

        mapRange(value, start, end) {
            value = Math.max(start, Math.min(value, end));

            return (value - start) / (end - start);
        },

        scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: "smooth",
            });
        },
    },
    mounted() {
        this.scrollUpButton = this.$refs.scrollUpButton;
        window.addEventListener("scroll", this.updateProgress);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.updateProgress);
    },
};
</script>

<style>
.scroll-up {
    position: fixed;
    right: 2rem;
    bottom: 2rem;
    background-color: var(--surface-container);
    color: var(--on-surface);
    border-radius: 50%;
    width: 4rem;
    height: 4rem;
    text-align: center;
    line-height: 4rem;
    font-size: 2rem;
    z-index: 2;
    visibility: hidden;
    opacity: 0;
    transform: translateY(1rem);
    transition: transform 0.4s ease, opacity 0.4s ease;
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
</style>
