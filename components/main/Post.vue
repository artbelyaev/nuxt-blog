<template>
  <el-card
    :body-style="{padding: 0}"
    shadow="hover"
    class="post"
  >
    <div class="post__header" slot="header">
      <h3 class="post__title">Post header</h3>
      <div class="post__time post-time">
        <i class="el-icon-time post-time__icon"></i>
        <span class="post-time__value">{{ new Date().toLocaleString() }}</span>
      </div>
    </div>
    <div class="post__body">
      <img src="https://www.slamdunk.ru/uploads/monthly_2022_09/301339779_1136171627110364_2025696225156905204_n.jpg.d07368111d1f83e45254663b75866b96.jpg" alt="post image" class="post__image">
    </div>
    <div class="post__footer">
      <el-button @click="openPost" round class="post__button">Открыть</el-button>
      <div class="post__comments post-comments">
        <i class="el-icon-s-comment post-comments__icon"></i>
        <span class="post-comments__count">12</span>
      </div>
    </div>
  </el-card>
</template>

<script>
export default {
  methods: {
    openPost() {
      console.log('Open post!');
    }
  }
}
</script>

<style lang="scss" scoped>
  .post {
    margin-bottom: 15px;

    &__header {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    &__image {
      width: 100%;
      height: auto;
    }

    &__footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px;
    }
  }
</style>
