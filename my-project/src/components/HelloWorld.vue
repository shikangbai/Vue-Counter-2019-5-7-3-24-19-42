<template>
  <div class="hello">
    <h1>click me</h1>
    <h2>counter</h2>
    <input type="number" v-model.number="num" />
    <div v-for="n in getNum" v-bind:key="n">
      <counter
        v-bind:index="n"
        msg="Welcome to Your Vue.js App"
        @listenCountChange="listenCountChange"
      />
    </div>
    <div>总和：{{total}}</div>
  </div>
</template>
<script>
import counter from "./Counter";
export default {
  name: "HelloWorld",
  data() {
    return {
      num: 0,
      count: 0,
      total: 0
    };
  },
  components: {
    counter
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
    },
    print() {
      console.log("butter clicked");
    },
    listenCountChange(num) {
      this.total += num;
    }
  },
  computed: {
    getNum: function() {
      return this.num;
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
span {
  margin-right: 20px;
  margin-left: 20px;
}
</style>