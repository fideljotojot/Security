<script>
import Signup from './components/SignupForm.vue';

export default {
  components: {
    Signup
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

        </div>
        <div class="form-container">
          <div class="form-box">
            <Signup/>
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
  padding: 1em;
  background-color: #A2AF9B;
}

button {
  padding: .5em .8em;
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
}

.logo-container {
  flex: 1;
}

.form-container {
  flex: 1;
  padding: 2em;
}

.form-box {
  width: 40em;
  height: 40em;
  border: none;
  border-radius: 1em;
  background-color: #4b4b4b;
}

footer {
  color: #4b4b4b;
  margin-top: auto;
  text-align: center;
  background-color: #a2af9b9a;
  padding: .8em;
}
</style>
