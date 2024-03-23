<template>
    <div class="login">
        <h1>User Account</h1>
        <form @submit.prevent="handleLogin" class="login-form">
            <label for="username">Username:</label>
            <input id="username" v-model="username" type="text" required>
            <label for="password">Password:</label>
            <input id="password" v-model="password" type="password" required>
            <button type="submit">{{ buttonText }}</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            username: 'admin',
            password: 'admin',
            defaultUsername: 'admin',
            defaultPassword: 'admin',
            isLoggedIn: !!localStorage.getItem('token'),
        }
    },
    computed: {
        buttonText() {
            return this.isLoggedIn ? 'Logout' : 'Login';
        }
    },
    methods: {
        handleLogin() {
            if (this.isLoggedIn) {
                alert('Successfully Logged out!');
                localStorage.removeItem('token');
                this.isLoggedIn = false;
                this.$router.push('/');
            } else {
                if (this.username == this.defaultUsername && this.password == this.defaultPassword) {
                    alert('Successfully Logged in!');
                    localStorage.setItem('token', '12345');
                    this.isLoggedIn = true;
                    this.$router.push('/', { name: 'profile' });
                } else {
                    alert('Invalid username or password!');
                }
            }
        }
    }
}
</script>