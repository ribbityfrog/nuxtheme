<script setup lang="ts">

const props = defineProps({
    debug: {
        type: Boolean,
        default: false
    }
})

const debugP = `${props.debug ? 'border-4 border-primary' : ''}`

</script>

<template>
    <div :class="`flex flex-col items-center min-h-screen w-full font-text leading-snug ${debugP}`">
        <slot />
    </div>
</template>
