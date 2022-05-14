<template>
    <form>
        <label>Name</label>
        <input
            type="text"
            class="form-control"
            id="name"
            v-model="form.name"
            placeholder="Name"
        />
        <label>Email address</label>
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
        <button type="button" @click="register">
        Login
        </button>
    </form>
</template>

<script>

export default {
    name: "Register",
    data: function() {
        return {
            form: {
                name: '',
                email: '',
                password: ''
            }
        }
    },
    methods: {
        register() {
            this.$store.dispatch('register', this.form).then(() => {
                this.$router.push({
                    name: 'Login'
                })
            })
        }
    }
};
</script>