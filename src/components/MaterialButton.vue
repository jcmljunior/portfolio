<template>
    <button ref="rippleEffect" class="ripple-button" :class="`${size}`">
        <slot></slot>
        <span ref="ripple" class="ripple light"></span>
    </button>
</template>

<script setup>
import { defineProps, onMounted, onBeforeUnmount, ref } from 'vue';

const ripple = ref(null)
const rippleEffect = ref(null)
const props = defineProps({
    href: {
        type: String,
        required: true,
    },
    target: {
        type: String,
        required: false,
        default: '_blank'
    },
    size: {
        type: String,
        required: false,
        default: 'btn-large'
    }
})

async function handleClick(e) {
    const button = e.currentTarget;
    // Captura a posição absoluta do botão.
    // Correção de offsetLeft e offsetTop em layout flex.
    const rect = button.getBoundingClientRect();
    const diameter = Math.max(button.clientWidth, button.clientHeight);
    const radius = diameter / 2;

    if (!ripple.value) return
    ripple.value.style.width = `${diameter}px`;
    ripple.value.style.height = `${diameter}px`;
    // ripple.value.style.left = `${e.clientX - button.offsetLeft - radius}px`;
    // ripple.value.style.top = `${e.clientY - button.offsetTop - radius}px`;
    ripple.value.style.left = `${e.clientX - rect.left - radius}px`;
    ripple.value.style.top = `${e.clientY - rect.top - radius}px`;
    ripple.value.classList.remove("active");
    void ripple.value.offsetWidth;
    ripple.value.classList.add("active")

    setTimeout(() => {
        window.open(props.href, props.target)
    }, 300);
}

onMounted(() => {
    rippleEffect.value?.addEventListener("click", handleClick)
});

onBeforeUnmount(() => {
    rippleEffect.value?.removeEventListener("click", handleClick)
});
</script>

<style scoped>
[class*="btn-"],
[class^="btn-"] {
    position: relative;
    display: inline-block;
    border-radius: 0.25rem;
    border: none;
    background-color: var(--primary);
    color: var(--on-primary);
    text-decoration: initial;
    overflow: hidden;
    transition: all 0.3s ease-in-out;

    &:hover {
        /* background-color: var(--primary-fixed-dim); */
        /* color: var(--primary-fixed); */
        cursor: pointer;
    }
}

.btn-small {
    padding: 0.5rem 1rem;
    font-size: 0.8125rem;
}

.btn-medium {
    padding: 0.75rem 1.5rem;
    font-size: 0.9375rem;
}

.btn-large {
    padding: 1rem 2rem;
    font-size: 1.125rem;
}

.ripple {
    position: absolute;
    border-radius: 50%;
    transform: scale(0);
    pointer-events: none;
}

.ripple.light {
    background: rgba(255, 255, 255, 0.6);
}

.ripple.dark {
    background: rgba(0, 0, 0, 0.6);
}

.ripple.active {
    animation: ripple-animation 0.6s ease-in-out;
}

@keyframes ripple-animation {
    to {
        transform: scale(4);
        opacity: 0;
    }
}
</style>
