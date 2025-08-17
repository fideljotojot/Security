<template>
  <form action="" method="POST">
    <h1>Register</h1>

    <div class="header">
      <h3>Personal Details</h3>
    </div>
    <hr>
    <div class="registration-box">
      <div class="form-group">
        <input type="text" id="id" name="id" required>
        <label for="id">ID No.</label>
      </div>
      <div class="form-group">
        <input type="text" id="fname" name="fname" required>
        <label for="fname">First Name:</label>
      </div>
      <div class="form-group">
        <input type="text" id="lname" name="lname" required>
        <label for="lname">Last Name:</label>
      </div>
      <div class="form-group">
        <input type="text" id="mname" name="mname" required>
        <label for="mname">Middle Initial:</label>
      </div>
      <div class="form-group">
        <input type="text" id="mname" name="mname" required>
        <label for="mname">Middle Initial:</label>
      </div>
      <div class="form-group">
        <input type="text" id="suffix" name="suffix">
        <label for="suffix">Suffix:</label>
      </div>
      <div class="form-group">
        <input type="text" id="birthdate" name="birthdate" required>
        <label for="birthdate">Birthdate:</label>
      </div>
      <div class="form-group">
        <input type="text" id="age" name="age" required>
        <label for="age">Age:</label>
      </div>
      <div class="form-group">
        <input type="text" id="username" name="username" required>
        <label for="username">Username:</label>
      </div>
      <div class="form-group">
        <input type="text" id="mname" name="mname" required>
        <label for="mname">Middle Initial:</label>
      </div>
      <div class="form-group">
        <select name="sex" id="sex" required>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select>
        <label for="mname">Sex:</label>
      </div>
    </div>

    <div class="header">
      <h3>Address</h3>
    </div>
    <hr>
    <div class="registration-box">
      <div class="form-group">
        <input type="text" id="purok" name="purok" required>
        <label for="purok">Purok:</label>
      </div>
      <div class="form-group">
        <input type="text" id="barangay" name="barangay" required>
        <label for="barangay">Barangay:</label>
      </div>
      <div class="form-group">
        <input type="text" id="city" name="city" required>
        <label for="city">City/Municipality:</label>
      </div>
      <div class="form-group">
        <input type="text" id="province" name="province" required>
        <label for="province">Province:</label>
      </div>
      <div class="form-group">
        <input type="text" id="country" name="country" required>
        <label for="country">Country:</label>
      </div>
      <div class="form-group">
        <input type="text" id="zip" name="zip" required>
        <label for="zip">Zip Code:</label>
      </div>
    </div>
    <div class="header">
      <h3>Login Details</h3>
    </div>
    <hr>
    <div class="registration-box">
      <div class="form-group">
        <input type="text" id="password" name="password" required>
        <label for="password">Password:</label>
      </div>
      <div class="form-group">
        <input type="text" id="repassword" name="repassword" required>
        <label for="repassword">Re-enter Password:</label>
      </div>
      <div class="form-group">
        <input type="text" id="email" name="email" required>
        <label for="email">Email:</label>
      </div>
    </div>

    <button class="btn"><a href="">Register</a></button>
</form>
</template>

<script>
</script>

<style scoped>
form {
    border-radius: 1.5em;
    padding: 1em;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1em;
}

.registration-box {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1em;
}

.form-group {
    display: flex;
    flex-direction: column-reverse;
}

.header {
    width: 100%;
    text-align: start;
    padding-left: 8em;
}

hr {
    width: 85%;
    margin: 0 0 1em 0;
}

.form-group input, select {
    padding: .5em 0 .5em 1em;
    border-radius: 1em;
    border: 1px solid #111;
}

.btn {
    border-radius: .9em;
    padding: .5em 1em;
}

a {
    text-decoration: none;
    color: #111;
}
</style>
