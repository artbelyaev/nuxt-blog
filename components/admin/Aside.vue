<template>
    <el-menu
        router
        :default-active="$route.path"
        class="aside-menu"
    >
        <el-menu-item index="/admin">
            <i class="el-icon-menu"></i>
            <span>Аналитика</span>
        </el-menu-item>
        <el-menu-item index="/admin/create">
            <i class="el-icon-edit-outline"></i>
            <span>Создать</span>
        </el-menu-item>
        <el-menu-item index="/admin/list">
            <i class="el-icon-tickets"></i>
            <span>Посты</span>
        </el-menu-item>
        <el-menu-item index="/admin/users">
            <i class="el-icon-user"></i>
            <span>Пользователи</span>
        </el-menu-item>
        <el-menu-item index="/admin/logout">
            <i class="el-icon-back"></i>
            <span>Выход</span>
        </el-menu-item>
    </el-menu>
</template>

<script>
export default {
    name: 'Aside'
};
</script>

<style lang="scss" scoped>
    .aside-menu {
        height: 100%;
    }
</style>
