<template>
    <form>
        <label for="email">Email address</label>
        <input
            type="email"
            id="email"
            v-model="form.email"
            placeholder="Email"
        />
        <label for="password">Password</label>
        <input
            type="password"
            v-model="form.password"
            placeholder="Password"
        />
        <button type="button" @click="login">
        Login
        </button>
    </form>
</template>

<script>

export default {
    name: "Login",
    data: function() {
        return {
            form: {
                email: 'mael.vidament@gmail.com',
                password: 'admin123'
            }
        }
    },
    methods: {
        login() {
            this.$store.dispatch('login', this.form).then(() => {
                this.$router.push({
                    name: 'Home'
                })
            })
        }
    }
};

</script>