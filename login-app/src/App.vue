<template>
  <div class="login-container">
    <form class="login-form" @submit.prevent="handleLogin">
      <h2>Login</h2>
      <div class="input-group">
        <label for="username">Username</label>
        <input id="username" v-model="username" type="text" required />
      </div>
      <div class="input-group">
        <label for="password">Password</label>
        <input id="password" v-model="password" type="password" required />
      </div>
      <button type="submit">Login</button>
      <p v-if="error" class="error">{{ error }}</p>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const username = ref('');
const password = ref('');
const error = ref('');

function handleLogin() {
  error.value = '';
  if (username.value === 'admin' && password.value === 'password') {
    alert('Login successful!');
  } else {
    error.value = 'Invalid username or password.';
  }
}
</script>

<style scoped>
.login-container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1200&q=80') no-repeat center center fixed;
  background-size: cover;
}
.login-form {
  background: #fff;
  padding: 2.5rem 2rem;
  border-radius: 1rem;
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.2);
  width: 100%;
  max-width: 350px;
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}
.login-form h2 {
  margin-bottom: 0.5rem;
  color: #3358e0;
  text-align: center;
}
.input-group {
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}
.input-group label {
  font-size: 1rem;
  color: #333;
}
.input-group input {
  padding: 0.7rem;
  border: 1px solid #d1d5db;
  border-radius: 0.5rem;
  font-size: 1rem;
  outline: none;
  transition: border 0.2s;
}
.input-group input:focus {
  border-color: #3358e0;
}
button[type="submit"] {
  background: #3358e0;
  color: #fff;
  border: none;
  padding: 0.8rem;
  border-radius: 0.5rem;
  font-size: 1.1rem;
  cursor: pointer;
  transition: background 0.2s;
}
button[type="submit"]:hover {
  background: #4f8cff;
}
.error {
  color: #e03a3a;
  text-align: center;
  margin-top: -0.5rem;
}
</style>
