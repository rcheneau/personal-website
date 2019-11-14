<template>
    <transition name="expand" @enter="enter" @after-enter="afterEnter" @leave="leave">
        <slot></slot>
    </transition>
</template>

<script>
    export default {
        name: "TransitionExpand",
        methods: {
            enter(element) {
                // To get height, has to set to auto -> hide it while doing it
                element.style.width = getComputedStyle(element).width;
                element.style.position = 'absolute';
                element.style.visibility = 'hidden';
                element.style.height = 'auto';

                const height = getComputedStyle(element).height;

                element.style.width = null;
                element.style.position = null;
                element.style.visibility = null;
                element.style.height = '0';

                setTimeout(() => {
                    element.style.height = height;
                });
            },
            afterEnter(element) {
                element.style.height = 'auto';
            },
            leave(element) {
                element.style.height = getComputedStyle(element).height;
                setTimeout(() => {
                    element.style.height = '0';
                });
            },
        }
    }
</script>

<style scoped>
    .expand-enter-active,
    .expand-leave-active {
        transition: height 1s ease-in-out;
        opacity: 0;
        overflow: hidden;
    }

    .expand-enter,
    .expand-leave-to {
        height: 0;
    }

    * {
        will-change: height;
        transform: translateZ(0);
        backface-visibility: hidden;
        perspective: 1000px;
    }
</style>