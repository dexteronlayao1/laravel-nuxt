<template>
  <div>
    <h1>Dashboard</h1>
    <button @click="handleCallTestAPI">Call TEST API</button>
    <button @click="handleLogout">Logout</button>
  </div>
</template>

<script>
export default {
  methods: {
    handleLogout() {
      this.$auth.logout().then(() => {
        this.$router.push("auth/login");
      });
    },
    handleCallTestAPI() {
      this.$axios
        .get("/api/test")
        .then((response) => console.log(response.data));
    },
  },
};
</script>

<style>
</style>