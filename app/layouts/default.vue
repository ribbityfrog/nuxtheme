<script setup lang="ts">

</script>

<template>
    <Layout>
        <Section full class="py-4">
            <HeaderMobile v-if="$device.isMobile" menu="main" />
            <HeaderDefault v-else menu="main" />
        </Section>
        <Section group full class="grow py-4">
            <slot />
        </Section>
        <footer class="w-full">
            <Section wide class="bg-neutral-300 dark:bg-neutral-950 py-4">
                <FooterDefault />
            </Section>
        </footer>
    </Layout>
</template>
