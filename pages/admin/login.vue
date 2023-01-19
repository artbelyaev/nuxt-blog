<template>
    <el-card
        shadow="always"
        class="login"
    >
        <el-form
            :model="controls"
            :rules="rules"
            ref="form"
            label-width="120px"
            class="login__form"
        >
            <h1 class="login__title">Авторизация</h1>
            <el-form-item label="Логин" prop="login">
                <el-input v-model.trim="controls.login" />
            </el-form-item>
            <el-form-item label="Пароль" prop="password">
                <el-input show-password v-model.trim="controls.password" />
            </el-form-item>
            <el-form-item>
                <el-button
                    @click="login"
                    :loading="loading"
                    round
                    type="primary"
                    class="login__button"
                >
                    Войти
                </el-button>
            </el-form-item>
        </el-form>
    </el-card>
</template>

<script>
export default {
    name: 'login',
    layout: 'empty',
    data() {
        return {
            loading: false,
            controls: {
                login: '',
                password: '',
            },
            rules: {
                login: [
                    {required: true, message: 'Пожалуйста введите логин', trigger: 'blur'},
                ],
                password: [
                    {required: true, message: 'Пожалуйста введите пароль', trigger: 'blur'},
                    {min: 6, message: 'Пароль должен быть не менее 6 символов', trigger: 'blur'},
                ],
            }
        };
    },
    methods: {
        login() {
            this.$refs.form.validate(async (valid) => {
                if (valid) {
                    this.loading = true;

                    try {
                        const formData = {
                            login: this.controls.login,
                            password: this.controls.password,
                        };

                        await this.$store.dispatch('login/login', formData);
                        this.$router.push('/admin');


                    } catch (e) {
                        this.loading = false;
                    }
                }
            });
        }
    }
};
</script>

<style lang="scss" scoped>
    .login {
        width: 500px;

        &__title {
            text-align: center;
            margin-bottom: 15px;
        }

        &__button {
            margin-top: 10px;
        }
    }
</style>
