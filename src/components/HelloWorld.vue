<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{ calcState }}</p>
    <Knob :state.sync="state"></Knob>
  </div>
</template>

<script>
import Knob from '@/components/Knob.vue'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      state: 'off'
    }
  },
  computed: {
    calcState: function () {
      return this.state
    }
  },
  components: {
    Knob
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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
