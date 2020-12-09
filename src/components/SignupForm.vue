<template>
  <h1>Signup Form</h1>
  <h2>Start using this webapp today!</h2>
  <form v-on:submit.prevent>
    <div class="input">
      <i class="fas fa-user"></i>
      <input type="text" placeholder="Username" required v-model="username" />
    </div>
    <div class="input">
      <i class="fas fa-envelope"></i>
      <input type="email" placeholder="Email" required v-model="email" />
    </div>
    <div class="input">
      <i class="fas fa-key"></i>
      <i
        class="fas fa-eye show-password"
        v-on:click="toggleShowPassword"
        v-if="!showPassword"
      ></i>
      <i
        class="fas fa-eye-slash show-password"
        v-on:click="toggleShowPassword"
        v-if="showPassword"
      ></i>
      <input
        ref="passwordInput"
        type="password"
        placeholder="Password"
        required
        v-model="password"
      />
    </div>
    <div class="input password-strength">
      <div class="password-srength-indicator"></div>
      <div class="password-srength-indicator"></div>
      <div class="password-srength-indicator"></div>
      <div class="password-srength-indicator"></div>
    </div>
    <div class="input">
      <i class="fas fa-check"></i>
      <input
        type="password"
        placeholder="Confirm password"
        required
        v-model="confirmPassword"
      />
    </div>

    <div class="input terms">
      <input type="checkbox" required v-model="terms" />
      <p>Acccept terms and conditions</p>
    </div>
    <button>Signup</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      email: "",
      password: "",
      confirmPassword: "",
      role: "",
      terms: false,
      showPassword: false,
    };
  },
  updated(){
    this.showPassword ?
      this.$refs.passwordInput.type="text" : this.$refs.passwordInput.type="password"
  
  },
  methods: {
    toggleShowPassword() {
      this.showPassword = !this.showPassword;
    },
  },
};
</script>

<style>
</style>