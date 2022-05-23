<template>
  <div>
    <h1>Register</h1>
    <form action="">
      <h3>Email</h3>
      <input class="email" type="text" v-model="email" />

      <h3>Password</h3>
      <input class="password" type="password" v-model="password" />
      <input class="button" type="submit" />

      <h3>Repite la Password</h3>
      <input class="password" type="password" v-model="rpassword" />
      <input class="button" type="submit" />

      <h3>Nota</h3>
      <input class="text-box" type="text" v-model="nota" />
      <input class="button" type="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "RegisterForm",
  data() {
    return {
      email: "",
      password: "",
      rpassword: "",
      note: "",
    };
  },
};
</script>

<style scoped>
input {
  margin: 10px;
}
</style>
