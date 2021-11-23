<template>
  <div>
    <form action="" @submit.prevent="handleLogin">
      <input type="text" v-model="form.email" />
      <input type="text" v-model="form.password" />
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {},
    };
  },
  methods: {
    handleLogin() {
      this.$auth
        .loginWith("laravelJWT", {
          data: this.form,
        })
        .then(() => {
          this.$router.push("/dashboard");
        });
    },
  },
};
</script>

<style>
</style>