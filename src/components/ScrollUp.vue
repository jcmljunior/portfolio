<template>
    <a class="scroll-up" href="#" @click.prevent="scrollToTop">
        <font-awesome-icon :icon="['fas', 'arrow-up']" />
    </a>
</template>

<script>
export default {
    data() {
        return {
            progress: 0,
        };
    },
    methods: {
        updateProgress() {
            const scrollTop = window.scrollY;
            const scrollHeight = document.documentElement.scrollHeight;
            const clientHeight = document.documentElement.clientHeight;
            const scrollUpButton = document.querySelector(".scroll-up");

            this.progress = (scrollTop / (scrollHeight - clientHeight)) * 100;

            if (this.progress > 60) {
                scrollUpButton.classList.add("visible");
                return;
            }

            scrollUpButton.classList.remove("visible");
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
    background-color: #0099FF;
    border-radius: 50%;
    width: 4rem;
    height: 4rem;
    text-align: center;
    line-height: 4rem;
    font-size: 2rem;
    color: #fff;
    visibility: hidden;
    opacity: 0;
    transition: all 0.6s ease-in-out;
}

.scroll-up.visible {
    visibility: visible;
    opacity: 1;
}
</style>
