<template>
  <button @click="onClick" :class="theme">
     {{ currentState }}
  </button>
</template>

<script>
export default {
  name: 'Knob',
  props: {
    state: {
      type: String,
      default: 'on'
    }
  },
  data () {
    return {
      currentState: this.state
    }
  },
  computed: {
    theme: function () {
      return this.currentState === 'on' ? '' : 'dark'
    }
  },
  methods: {
    onClick: function (event) {
      this.currentState = ['on', 'off'].find(_ => _ !== this.currentState)
      this.$emit('stateChange', this.currentState)
    }
  }
}
</script>

<style scoped>
  button {
    font-size: 30px;
    padding: 4px 16px;
  }
  button.dark {
    background-color: #000;
    color: #fff;
  }
</style>
