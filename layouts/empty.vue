<template>
    <div class="empty-layout">
        <Nuxt />
    </div>
</template>

<script>
export default {
    name: 'empty'
};
</script>

<style lang="scss" scoped>
    .empty-layout {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        min-height: 100vh;
    }
</style>
