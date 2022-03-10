<template>
  <div class="navigation">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      name: "Header",
    };
  },
};
</script>

<style lang="scss" scoped>
nav {
    padding: 20px;
    background: #42b983;
    margin-bottom: 100px;
  a {
    margin: 5px;
    font-size: 20px;
    font-weight: bold;
    color: white;
    text-decoration: none;

    &.router-link-exact-active {
      color: #2c3e50;
    }
  }
}
</style>