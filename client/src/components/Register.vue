<template>
    <div>
        <h1>Register</h1>

        <input type="email" name="email" placeholder="email" v-model="email">
        <br>
        <input type="password" name="password" placeholder="password" v-model="password">
        <br>
        <button type="button" name="button" @click="register">Register</button>
    </div>
</template>

<script>
import AuthService from '@/services/AuthService'
export default {
    name: 'Register',
    data () {
        return {
            email: '',
            password: ''
        }
    },
    methods: {
        async register () {
            const response = await AuthService.register ({
                email: this.email,
                password: this.password
            })
            console.log (response.data)
        }
    }
}
</script>

<style scoped>
</style>
