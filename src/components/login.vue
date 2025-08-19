<template>
  <form action="" method="POST">
    <h1>Login</h1>
    <div class="form-content">
        <div class="form-group">
          <input type="text" id="username" name="username" required>
          <label for="username">Username:</label>
        </div>
        <div class="form-group">
          <input type="text" id="password" name="password" required>
          <label for="password">Password:</label>
        </div>
    </div>
    <div class="btn-container">
        <button type="button" class="btn" @click="$emit('go-home')">Login</button>
    </div>
</form>
</template>

<script>
export default {
  data() {
    return {
    }
  
  }
}

</script>

<style scoped>
form {
  height: 100%;
  padding: 1em;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5em;
}

.form-content {
  width: 100%;
  height: 100%;
  gap: 1em;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  background-color: #F1F0E4;
  padding: 1.5em;
  border-radius: 1em;
}

.form-group {
  display: flex;
  flex-direction: column-reverse;
  gap: .2em;
}

.form-group label {
  text-align: start;
  margin-left: 1em;
}

.form-group input, select {
  width: 90%;
  align-self: center;
  padding: .5em 0 .5em 1em;
  border-radius: 1em;
  border: 1px solid #111;
}

.header {
  width: 100%;
  text-align: start;
  margin-left: 1em;
}

h3 {
  font-weight: 600;
}

h1 {
  font-weight: bolder;
  text-transform: uppercase;
}

hr {
  width: 100%;
}

.btn-container {
  display: flex;
  gap: 1em;
  width: 100%;
  justify-content: center;
  margin-top: auto;
}

.btn {
  border-radius: .9em;
  padding: .8em 1.5em;
  border: none;
  background-color: #7D8D86;
  box-shadow: 1px 1px 1px #00000095;
  color: #F1F0E4;
  font-size: .9em;
}

.form-content > .btn {
  align-self: center;
  margin-top: auto;
}

a {
  text-decoration: none;
  color: #F1F0E4;
}
</style>
