<script setup lang="ts">
import type { BundledLanguage } from 'shiki'

const toast = useToast()

const props = defineProps({
    lang: {
        type: String as PropType<BundledLanguage>,
        default: 'ts'
    },
    code: {
        type: String,
        required: true
    },
    file: {
        type: String,
        required: true
    }
})

function clipboard() {
    navigator.clipboard.writeText(props.code)
    toast.add({ title: 'Copied!', description: 'Code copied to clipboard.', color: 'success' })
}

</script>

<template>
    <Flex col start>
        <Flex full between class="px-4 py-2 border-2 bg-muted">
            <p>
                {{ props.file }}
            </p>
            <UIcon name="i-lucide-clipboard" class="hover:animate-pulse cursor-pointer" @click="clipboard" />
        </Flex>
        <Shiki :lang="props.lang" :code="props.code" class="px-2 py-2 bg-inverted dark:bg-elevated border-x-2 border-b-2" />
    </Flex>
</template>
