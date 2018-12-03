<template>
  <div class="list">
    <ul v-for="(option, index) in options" :key="index">
      <li><slot :option="option" /></li>
      <!--
        {{
          customLabel(option)
        }}
      -->
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    options: Array,
    customLabel: Function
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
