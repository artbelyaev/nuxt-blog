<template>
    <article class="post">
        <div class="post__header post-header">
            <div class="post-header__top">
                <h1 class="post-header__title">Post title</h1>
                <NuxtLink to="/">
                    <i class="el-icon-back"></i>
                </NuxtLink>
            </div>
            <div class="post-header__info">
                <div class="post-header__time post-header-time">
                    <i class="el-icon-time post-header-time__icon"></i>
                    <span class="post-header-time__value">{{ new Date().toLocaleString() }}</span>
                </div>
                <div class="post-header__views post-header-views">
                    <i class="el-icon-view post-header-views__icon"></i>
                    <span class="post-header-views__count">25</span>
                </div>
            </div>
            <img src="https://www.slamdunk.ru/uploads/monthly_2022_09/301339779_1136171627110364_2025696225156905204_n.jpg.d07368111d1f83e45254663b75866b96.jpg" alt="post image" class="post-header__image" />
        </div>
        <div class="post__content">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto at consequatur, ducimus ea error incidunt laboriosam nostrum obcaecati officia unde?</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto at consequatur, ducimus ea error incidunt laboriosam nostrum obcaecati officia unde?</p>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto at consequatur, ducimus ea error incidunt laboriosam nostrum obcaecati officia unde?</p>
        </div>
        <div class="post__footer">
            <CommentForm @created="createComment" v-if="formVisibility" class="post__form" />
            <div v-if="true" class="post__comments">
                <Comment v-for="n in 4" :key="n" class="post__comment"/>
            </div>
            <div v-else class="post__empty">Комментариев нет</div>
        </div>
    </article>
</template>

<script>
import Comment from '@/components/main/Comment';
import CommentForm from '@/components/main/CommentForm';

export default {
    validate({params}) {
        return Boolean(params.id);
    },
    data() {
        return {
            formVisibility: true,
        };
    },
    components: {
        Comment, CommentForm,
    },
    methods: {
        createComment() {
            this.formVisibility = false;
        }
    }
};
</script>

<style lang="scss" scoped>
    .post {
        max-width: 600px;
        margin: 0 auto;

        &__header {
            margin-bottom: 15px;
        }

        &__content {
            margin-bottom: 20px;
        }

        &__empty {
            text-align: center;
        }

        &__comment {
            margin-bottom: 10px;
        }
    }

    .post-header {
        &__top,
        &__info {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        &__top {
            margin-bottom: 10px;
        }

        &__info {
            margin-bottom: 5px;
        }

        &__image {
            width: 100%;
            height: auto;
        }
    }
</style>
