<script>
import Signup from './components/SignupForm.vue';
import Login from './components/LoginForm.vue';

export default {
  components: {
    Signup,
    Login
  },
  data() {
    return {
      page: 'login'
    }
  }
}
</script>

<template>
  <div id="app">
    <header v-if="page === 'signup'">
      <button @click="page = 'home'">Home</button>
      <button @click="page = 'login'">Login</button>
    </header>
    <header v-if="page === 'login'">
      <button @click="page = 'home'">Home</button>
      <button @click="page = 'signup'">Sign Up</button>
    </header>
    <header v-if="page === 'home'">
      <button @click="page = 'login'">Login</button>
      <button @click="page = 'signup'">Sign Up</button>
    </header>

    <main>
      <div class="page-container" v-if="page === 'signup' || page === 'login'">
        <div class="logo-container">
          <h1>Logo here</h1>
        </div>
        <div class="form-container">
          <div class="form-box">
            <Signup v-if="page === 'signup'" @go-login="page = 'login'"/>
            <Login v-else-if="page === 'login'"/>
          </div>
        </div>
      </div>

      <div class="page-container" v-if="page === 'home'">
        <p>Home</p>
      </div>
    </main>

    <footer>
      <p>&copy;  2025 www.handy.com - All Rights Reserved</p>
    </footer>
  </div>
</template>

<style scoped>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

header {
  display: flex;
  justify-content: flex-end;
  gap: 1em;
  padding: .7em;
  background-color: #A2AF9B;
}

button {
  padding: .4em .8em;
  border: none;
  border-radius: 1em;
  box-shadow: 1px 1px 1px #00000087;
}

main {
  flex: 1;
  display: flex;
}

.page-container {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  padding: 0;
}

.logo-container {
  flex: 1;
  display: flex;
  justify-content: center;
}

.form-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90%;
  border-left: 1px solid grey;
}

.form-box {
  width: fit-content;
  height: fit-content;
  padding: 3em 2.5em;
  border: none;
  border-radius: 1em;
  background-color: #bca88dca;
}

footer {
  color: #4b4b4b;
  margin-top: auto;
  text-align: center;
  background-color: #a2af9b9a;
  padding: .5em;
  font-size: .8em;
}
</style>
