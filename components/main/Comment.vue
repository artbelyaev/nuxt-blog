<template>
    <el-card class="comment">
        <div class="comment__header">
            <span class="comment__author">Author name</span>
            <div class="comment__time comment-time">
                <i class="el-icon-time comment-time__icon"></i>
                <span class="comment-time__value">{{ new Date().toLocaleString() }}</span>
            </div>
        </div>
        <div class="comment__text">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto aspernatur cupiditate debitis eligendi fugiat harum id ipsam reiciendis rem sequi.
        </div>
    </el-card>
</template>

<script>
export default {
    name: 'Comment',
    props: ['comment'],
};
</script>

<style lang="scss" scoped>
    .comment {
        &__header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        &__author {
            font-size: 12px;
        }

        &__text {
            white-space: pre-line;
        }
    }

    .comment-time {
        display: flex;
        align-items: center;

        &__value {
            margin-left: 5px;
            font-size: 12px;
        }
    }
</style>
