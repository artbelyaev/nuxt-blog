<template>
    <el-form
        :model="controls"
        :rules="rules"
        ref="form"
        label-width="120px"
        class="comment-form"
    >
        <h1 class="comment-form__title">Добавить комментарии</h1>
        <el-form-item label="Имя" prop="name">
            <el-input v-model.trim="controls.name" />
        </el-form-item>
        <el-form-item label="Комментарий" prop="text">
            <el-input type="textarea" resize="none" :rows="2" v-model.trim="controls.text" />
        </el-form-item>
        <el-form-item>
            <el-button
                @click="onSubmit"
                :loading="loading"
                round
                type="primary"
            >
                Create
            </el-button>
        </el-form-item>
    </el-form>
</template>

<script>
export default {
    name: 'CommentForm',
    data() {
        return {
            loading: false,
            controls: {
                name: '',
                text: '',
            },
            rules: {
                name: [
                    {required: true, message: 'Пожалуйста введите имя', trigger: 'blur'},
                ],
                text: [
                    {required: true, message: 'Пожалуйста введите ваш комментарий', trigger: 'blur'},
                ],
            }
        };
    },
    methods: {
        onSubmit() {
            this.$refs.form.validate((valid) => {
                if (valid) {
                    this.loading = true;
                    const formData = {
                        name: this.controls.name,
                        text: this.controls.text,
                        postId: '',
                    };

                    try {
                        setTimeout(() => {
                            this.$message.success('Комментарий добавлен');
                            this.$emit('created');
                        }, 2000);
                    } catch (e) {
                        this.loading = false;
                    }
                } else {
                    console.log('error submit!!');
                    return false;
                }
            });


        }
    }
};
</script>

<style lang="scss" scoped>
    .comment-form {
        &__title {
            margin-bottom: 15px;
        }
    }
</style>
