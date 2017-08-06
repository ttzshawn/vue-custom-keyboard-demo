<template>
  <div class="hello">
    <h2>Vue Custom Keyboard Example</h2>
    <h1 class="title"  @click="showKeyboard">{{ inputValue }}</h1>
    <VueCustomKeyboard
      :isOpen="isOpen"
      :onChange="onChange"
      :onBlur="onBlur"
      :onDone="onDone"
    >
    </VueCustomKeyboard>
  </div>
</template>

<script>
import VueCustomKeyboard from 'vue-custom-keyboard'
import 'vue-custom-keyboard/dist/vue-custom-keyboard.min.css'

export default {
  name: 'demo',
  components: {
    VueCustomKeyboard
  },
  data () {
    return {
      inputValue: '',
      isOpen: true
    }
  },
  methods: {
    onChange (value) {
      this.inputValue = value
    },
    onBlur () {
      this.isOpen = false
    },
    onDone () {
      this.isOpen = false
    },
    showKeyboard () {
      this.isOpen = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title {
  width: 200px;
  height: 44px;
  margin: 0 auto;
  text-align: center;
  border: 1px solid lightblue;
}
</style>
