<template>
  <div class="hello">
    <h1>我是史康柏</h1>
    {{count}}
    <button @click="add()">+</button>
    <button @click="down()">-</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      count: 0
    };
  },
  props: {
    msg: String
  },
  methods: {
    add: function() {
      this.count++;
    },
    down: function() {
      this.count--;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
