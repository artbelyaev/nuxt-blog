<template>
    <div class="error-layout">
        <div class="error-layout__content">
            <h1 class="error-layout__title">404</h1>
            <NuxtLink to="/" class="error-layout__link">Вернуться на главную</NuxtLink>
        </div>
    </div>
</template>

<script>
export default {
    name: 'error'
};
</script>

<style lang="scss" scoped>
    .error-layout {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;

        &__content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        &__title {
            margin-bottom: 15px;
            color: hsl(0, 94%, 35%);
        }
    }
</style>
