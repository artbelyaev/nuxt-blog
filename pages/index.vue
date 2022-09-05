<template>
  <el-row type="flex" justify="center">
    <el-col :xs="24" :sm="18" :md="12" :lg="10">
      <Post v-for="n in 5" :key="n"></Post>
    </el-col>
  </el-row>
</template>

<script>
import Post from '@/components/main/Post'
export default {
  name: 'IndexPage',
  components: {
    Post,
  },
  head: {
    title: 'Главная страница',
  }
}
</script>
