<template>
    <a class="scroll-up" href="#" @click.prevent="scrollToTop">
        <font-awesome-icon :icon="['fas', 'arrow-up']" />
    </a>
</template>

<script>
export default {
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
            const scrollUpButton = document.querySelector(".scroll-up");
            const startAnimation = 50;
            const endAnimation = 70;

            this.interpolation = scrollTop / (scrollHeight - clientHeight);
            this.progress = this.interpolation * 100;

            this.showScrollButton = this.progress > 60;
            scrollUpButton.style.visibility = this.progress > startAnimation ? "visible" : "hidden";
            scrollUpButton.style.opacity = this.lerp(0, 1, this.mapRange(this.progress, startAnimation, endAnimation));
            scrollUpButton.style.transform = `translateY(${this.lerp(0, 1, this.mapRange(this.progress, startAnimation, endAnimation))}rem)`;
        },

        lerp(a, b, t) {
            t = Math.max(0, Math.min(1, t));
            return a + (b - a) * t;
        },

        mapRange(value, start, end) {
            value = Math.max(start, Math.min(value, end));
            start = Math.min(start, end);
            end = Math.max(start, end);

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
    visibility: hidden;
    opacity: 0;
    transition: all 0.6s ease-in-out;
    z-index: 2;
}

.scroll-up:hover {
    background-color: var(--surface-container-highest);
    cursor: pointer;
}
</style>
