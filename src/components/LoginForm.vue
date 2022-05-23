<template>
  <div>
    <h1>Login</h1>
    <form action="">
      <h3>Email</h3>
      <input class="email" type="text" v-model="email" />

      <h3>Password</h3>
      <input class="password" type="password" v-model="password" />
      <input class="button" type="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    };
  },
};
</script>

<style scoped>
input {
  margin: 10px;
}
</style>
