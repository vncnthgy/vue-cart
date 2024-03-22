<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="100" height="100" />

    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/product">Product</RouterLink>
        <RouterLink to="/login">Login</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}

div {
  color: white;
  font-family: Arial, sans-serif;
}

h1 {
  color: white;
  margin: 10px;
  text-align: center;
}

h2 {
  color: white;
  margin: 10px;
  text-align: right;
}

hr {
  border: none;
  margin: 10px;
  border-top: 1px solid white;
}

span {
  display: inline;
  margin: 10px;
  font-size: 18px;
  color: white;
}

.item {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.item-container {
  border: 1px solid grey;
  margin: 10px;
  padding: 5px;
}

.row {
  display: flex;
  justify-content: space-between;
}

.left, .right {
  flex: 1;
}

.add-button {
  color: white;
  background-color: green;
  border: none;
  padding: 10px 30px;
  text-align: center;
  display: inline;
  font-size: 15px;
  margin: 6px 3px;
  cursor: pointer;
  border-radius: 30px;
}

.remove-button {
  color: white;
  background-color: red;
  border: none;
  padding: 10px 30px;
  text-align: center;
  display: inline;
  font-size: 15px;
  margin: 6px 3px;
  cursor: pointer;
  border-radius: 30px;
}

.qty-button {
  color: white;
  background-color: blue;
  border: none;
  padding: 10px 15px;
  text-align: center;
  display: inline;
  font-size: 15px;
  margin: 6px 3px;
  cursor: pointer;
  border-radius: 30%;
}

.login-form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: 10px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
}

.login-form label {
  margin-bottom: 10px;
}

.login-form input {
  margin-bottom: 20px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.login-form button {
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.login-form button:hover {
  background-color: #45a049;
}
</style>