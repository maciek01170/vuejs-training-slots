<template>
  <div>
    <h1>List of attendees</h1>
    <div id="app">
      <List :options="options" :customLabel="customLabel">
        <template slot-scope="{ option }">
          {{ option.lastName }}, {{ option.firstName }},
          <a :href="`mailto:${option.email}`">{{ option.email }}</a>
        </template>
      </List>
    </div>
  </div>
</template>

<script>
import List from "./components/List";

export default {
  name: "App",
  components: {
    List
  },
  methods: {
    getemail(option) {
      return option.email;
    },
    customLabel(option) {
      return (
        option.lastName +
        " " +
        option.firstName +
        " " +
        '<a href="mailto:' +
        option.email +
        '"> ' +
        option.email +
        "</a>"
      );
    }
  },
  data() {
    return {
      options: [
        {
          firstName: "John",
          lastName: "Snow",
          email: "john@winterfell.com"
        },
        {
          firstName: "Frodo",
          lastName: "Baggins",
          email: "frodo@bagend.com"
        },
        {
          firstName: "Lara",
          lastName: "Croft",
          email: "lara@tombraider.com"
        },
        {
          firstName: "Clark",
          lastName: "Kent",
          email: "clark@dailyplanet.com"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
