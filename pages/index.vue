<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">vue_test</h1>
      <h2 class="subtitle">My finest Nuxt.js project</h2>
    </div>
    <div>
      <nuxt-link to="/list">list</nuxt-link>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {
  components: {
    Logo
  },
  mounted() {
    this.$axios
      .post("https://op.huishoubao.com/index/index", {
        _head: {
          _version: "0.01",
          _msgType: "request",
          _timestamps: "1571645493",
          _interface: "PlatProfit.getEnv",
          _remark: ""
        },
        _param: {
          user_id: "1227",
          login_token: "146fb8f8405f99974df2443413a2c061"
        }
      })
      .then(res => {
        console.log(res);
      });
  }
};
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
</style>
