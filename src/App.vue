<script>
import Signup from './components/SignupForm.vue';
import Login from './components/LoginForm.vue';
import Home from './components/HomePage.vue';

export default {
  components: {
    Signup,
    Login,
    Home
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
      <img src="./assets/images/Caraga_State_University_-_Cabadbaran_Campus_logo_(Reduced).png" alt="Logo">
      <div class="header-btn">
        <button @click="page = 'home'">Home</button>
        <button @click="page = 'login'">Login</button>
      </div>
    </header>
    <header v-if="page === 'login'">
      <img src="./assets/images/Caraga_State_University_-_Cabadbaran_Campus_logo_(Reduced).png" alt="Logo">
      <div class="header-btn">
        <button @click="page = 'home'">Home</button>
        <button @click="page = 'signup'">Sign Up</button>
      </div>
    </header>
    <header v-if="page === 'home'">
      <img src="./assets/images/Caraga_State_University_-_Cabadbaran_Campus_logo_(Reduced).png" alt="Logo">
      <div class="header-btn">
        <button @click="page = 'login'">Login</button>
        <button @click="page = 'signup'">Sign Up</button>
      </div>
    </header>

    <main>
      <div class="page-container" v-if="page === 'signup' || page === 'login'">
        <div class="logo-container">
          <img src="./assets/images/icon.png" alt=" Logo">
        </div>
        <div class="form-container">
          <div class="form-box">
            <Signup v-if="page === 'signup'" @go-login="page = 'login'"/>
              <Login v-else-if="page === 'login'" @go-home="page = 'home'"/>
          </div>
        </div>
      </div>

      <div class="page-container" v-if="page === 'home'">
        <Home/>
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
  background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url(./assets/images/background.jpg);
  background-size: cover;
}

header {
  display: flex;
  justify-content: flex-end;
  padding: 1em;
  background-color: #8cb67685;
}

header img {
  height: 3em;
  position: absolute;
  left: 1em;
  top: .5em;
}

header .header-btn {
  display: flex;
  justify-content: space-between;
  gap: 1em;
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

.logo-container img {
  filter: brightness(0) invert(1);
  margin: auto;
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
  padding: 1em 2.5em 2em;
  border: none;
  border-radius: 1em;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(10px);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
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
