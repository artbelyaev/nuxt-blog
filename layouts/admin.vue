<template>
    <el-container class="admin">
        <el-aside class="admin__aside">
            <Aside />
        </el-aside>
        <el-main>
            <Nuxt />
        </el-main>
    </el-container>
</template>

<script>
import Aside from '@/components/admin/Aside';
export default {
    name: 'admin',
    components: {
        Aside,
    }
};
</script>

<style lang="scss" scoped>
    .admin {
        width: 100%;
        height: 100vh;

        &__aside {
            width: 250px;
        }
    }
</style>
