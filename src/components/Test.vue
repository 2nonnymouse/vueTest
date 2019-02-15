<template>
  <div class="test">
    <!-- input binding -->
    <input type="text" v-model="title" /><br />
    <h1>{{ title }}</h1>
    <p>{{ user.firstName }}</p>
    <p v-text="user.firstName"></p>
    <p v-if="showName">{{ user.lastName }}</p>
    <p v-else="showName">{{ user.firstName }}</p>

    <ul>
      <li v-for="item in items">{{ item.title }}</li>
    </ul>
    <button v-on:click="greet">Say Greeting</button> <br />
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit" />
  </div>
</template>

<script>
export default {
  name: "test",
  data() {
    return {
      title: "Hello world",
      user: {
        firstName: "scott",
        lastName: "Iam"
      },
      showName: true,
      items: [
        { title: "Item One" },
        { title: "Item Two" },
        { title: "Item Three" }
      ]
    };
  },
  methods: {
    greet: function() {
      alert("Hello");
    },
    pressKey: function(e) {
      console.log("pressed");
      console.log(e.target.value);
    },
    enterHit: function() {
      console.log("You hit enter");
    }
  }
};
</script>

<style scoped></style>
