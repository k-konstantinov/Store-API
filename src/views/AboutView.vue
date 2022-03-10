<template>
  <div class="contactsView">
    <h3>Contact with Us</h3>

    <div class="container">
      <form v-if="!active">
        <label for="name">Name</label>
        <input type="text" placeholder="Your name.." v-model="name" />

        <label for="email">Email</label>
        <input type="email" placeholder="Your email.." v-model="email" />

        <label for="number">Phone number</label>
        <input type="number" placeholder="Your phone.." v-model="phone" />

        <label for="message">Message</label>
        <textarea
          id="subject"
          placeholder="Write something.."
          style="height: 200px"
          v-model="message"
        ></textarea>

        <button v-on:click="active='true'" class="submit">Submit</button>
      </form>
      <div v-else>
        <h2>Name: {{ name }}</h2> 
        <h2>Mail: {{ email }}</h2>
        <h2>Phone: {{ phone }}</h2>
        <h2>Message: {{ message }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutView",
  data() {
    return {
      name: "",
      email: "",
      phone: "",
      message: "",
      active: false
    };
  },
};
</script>

<style scoped>
.contactsView {
  width: 500px;
  display: inline-block;
}

input[type="text"],
input[type="email"],
input[type="number"],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

.submit {
  background-color: #42b983;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.submit:hover {
  background-color: #45a049;
}

.container {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
</style>