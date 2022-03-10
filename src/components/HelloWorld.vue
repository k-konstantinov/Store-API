<template>
<div id="main">
  <h1>Products</h1>
  <div class="product-box">
    <div v-for="product in data" :key="product.id" class="product">
      <div>
        <h2>
          {{ product.title }}
        </h2>
        <p>Category: {{ product.category }}</p>
      </div>
      <img :src="product.image" style="width: 300px; height: 350px" alt="" />
      <p class="bold">Price: {{ product.price }}&euro;</p>
      <router-link :to="{ name: 'SProduct', params: { id: product.id } }"><button class="view">View</button></router-link>
    </div>
  </div>
</div>
</template>

<script>

export default {
  name: "HelloWorld",  
  data() {
    return {
      data: "",
      input: "",
      api: "https://fakestoreapi.com/products?limit=9",
    };
  },
  mounted() {
    fetch(this.api)
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
.product:hover {
  transform: scale(1.1);
  transition: transform 0.8s,
}
.product-box {
  display: flex;
  flex-wrap: wrap;
  padding: 25px;
}
.product {
  position: relative;
  border: 1px solid #dad5d5;
  background-color: white;
  box-shadow: 10px 10px 5px #aaaaaa;
  width: 450px;
  height: 600px;
  margin: 25px;
  flex: 1 0;
}
.bold{
  font-weight: 600;
}
.view {
  cursor: pointer;
  margin-top: 20px;
  padding: 12px 20px;
  background: #42b983;
  color: white;
  border: none;
  border-radius: 4px;
  position: absolute;
  bottom: 40px;
  right: 20px;
}
</style>
