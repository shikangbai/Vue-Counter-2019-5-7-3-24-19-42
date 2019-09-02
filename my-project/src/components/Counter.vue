<template>
  <div class="counter">
    <span>{{index}}</span>
    <button @click="add()">+</button>
    {{count}}
    <button @click="down()">-</button>
  </div>
</template>

<script>
export default {
  name: "counter",
  data() {
    return {
      count: 0
    };
  },
  props: {
    msg: String,
    index: Number
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
    }
  },
  watch: {
    count: function(newVal, oldVal) {
      this.$emit("listenCountChange", newVal - oldVal);
    }
  },
  mounted() {
    this.count = this.index;
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