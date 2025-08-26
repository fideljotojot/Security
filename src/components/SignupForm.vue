<template>
  <form action="" method="POST">
    <h1>Register</h1>
    <div class="form-content" v-if="step === 'personal'">
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
          <input type="text" id="mname" name="mname" required>
          <label for="mname">Middle Initial:</label>
        </div>
        <div class="form-group">
          <input type="text" id="lname" name="lname" required>
          <label for="lname">Last Name:</label>
        </div>
        <div class="form-group">
          <input type="text" id="suffix" name="suffix">
          <label for="suffix">Suffix:</label>
        </div>
        <div class="form-group">
          <input type="date" id="birthdate" name="birthdate" required @input="calculateAge">
          <label for="birthdate">Birthdate:</label>
        </div>
        <div class="form-group">
          <small id="age-warning" class="warning"></small>
          <input type="text" id="age" name="age" required readonly>
          <label for="age">Age:</label>
        </div>
        <div class="form-group">
          <select name="sex" id="sex" required>
              <option value="male">Male</option>
              <option value="female">Female</option>
          </select>
          <label for="mname">Sex:</label>
        </div>
      </div>
      <button type="button" @click="step = 'address'" class="btn">Next</button>
    </div>

    <div class="form-content" v-if="step === 'address'">
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
      <div class="btn-container">
        <button type="button" @click="step = 'personal'" class="btn">Back</button>
        <button type="button" @click="step = 'login_details'" class="btn">Next</button>
      </div>
    </div>

    <div class="form-content" v-if="step === 'login_details'">
      <div class="header">
        <h3>Login Details</h3>
      </div>
      <hr>
      <div class="registration-box">
        <div class="form-group">
          <input type="text" id="username" name="username" required>
          <label for="username">Username:</label>
        </div>
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
      <div class="btn-container">
        <button type="button" @click="step = 'address'" class="btn">Back</button>
        <button type="button" class="btn" @click="$emit('go-login')">Register</button>
      </div>
    </div>
</form>
</template>

<script>
export default {
  data() {
    return {
      step: 'personal'
    }
  },
  methods: {
    calculateAge() {
      const dob = document.getElementById('birthdate').value;
      const warning = document.getElementById('age-warning');
      let messages = [];
      if (!dob) {
        document.getElementById('age').value = '';
        warning.textContent = '';
        return;
      }
      const dobDate = new Date(dob);
      const today = new Date();
      let age = today.getFullYear() - dobDate.getFullYear();
      const m = today.getMonth() - dobDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < dobDate.getDate())) {
        age--;
      }
      document.getElementById('age').value = age;

      if (isNaN(age) || age < 0) {
        messages.push('Age is invalid!');
      } else if (age < 18) {
        messages.push('Age is below 18 years old');
      }
      warning.textContent = messages.join('! ');
  }
  }
}

</script>

<style scoped>
form {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1em;
}

.form-content {
  width: 100%;
  height: 80%;
  gap: .5em;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #F1F0E4;
  padding: 1.5em 2em;
  border-radius: 1em;
  margin: auto;
}

.registration-box {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1em 1em .5em 1em;
  width: 100%;
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
  padding: .5em .5em .5em 1em;
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
  margin-top: 3em;
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
