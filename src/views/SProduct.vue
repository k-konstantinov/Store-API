<template>
  <div class="product">
    <div>
      <h1>
        {{ data.title }}
      </h1>
      <p>Category: {{ data.category }}</p>
    </div>
    <img :src="data.image" style="width: 300px; height: 350px" alt="" />
    <router-link to="/"><button class="view">Back</button></router-link>
  </div>
</template>

<script>
export default {
  name: "SProduct",
  props: ["id"],
  data() {
    return {
      data: "",
    };
  },
  mounted() {
    fetch("https://fakestoreapi.com/products/" + this.id)
      .then((response) => {
        return response.json();
      })
      .then((result) => {
        this.data = result;
      })
      .catch((err) => {
        console.log(err.message);
      });
  },
};
</script>


<style scoped>
.view {
  cursor: pointer;
  margin-top: 20px;
  padding: 12px 20px;
  background: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  position: absolute;
  left: 300px;
}
</style>
