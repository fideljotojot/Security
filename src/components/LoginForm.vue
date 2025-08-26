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
      <div class="btn-container">
          <button type="button" class="btn" @click="$emit('go-home')">Login</button>
      </div>
    </div>
  </form>
</template>

<script>

</script>

<style scoped>
form {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1em;
}

h1 {
  font-weight: bolder;
  text-transform: uppercase;
  margin-bottom: .5em;
}

.form-content {
  width: 25em;
  height: 20em;
  gap: 1em;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #F1F0E4;
  padding: 1em 2em;
  border-radius: 1em;
  margin: auto 0;
}

.form-group label {
  text-align: start;
  margin-left: 1em;
}

.form-group {
  display: flex;
  flex-direction: column-reverse;
  gap: .2em;
}

.form-group input, select {
  width: 90%;
  align-self: center;
  padding: .5em .5em .5em 1em;
  border-radius: 1em;
  border: 1px solid #111;
}

.btn-container {
  display: flex;
  gap: 1em;
  width: 100%;
  justify-content: center;
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
</style>
