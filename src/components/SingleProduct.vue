<template>
  <div class="home">
    <HelloWorld />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  props: ["id"],
  data() {
    return {
        data: '',
    }
  },
  components: {
    HelloWorld,
  },
};
</script>
