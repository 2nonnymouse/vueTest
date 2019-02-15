<template>
  <div class="test">
    <!-- input binding -->
    <input type="text" v-model="title" /><br />
    <h1>{{ title }}</h1>
    <p>{{ user.firstName }}</p>
    <p v-text="user.firstName"></p>
    <p v-if="showName">{{ user.lastName }}</p>
    <p v-else="showName">{{ user.firstName }}</p>
    <br />
    <!-- computed properties used to watch things and update properties -->
    <label>First Name: </label><input type="text" v-model="user.firstName" />
    <br />
    <label>Last Name: </label><input type="text" v-model="user.lastName" />
    <h1>{{ fullName }}</h1>
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
    },
    computed: {
      fullName: function() {
        return;
        this.user.firstName + " " + this.user.lastName;
      }
    }
  }
};
</script>

<style scoped></style>
