<template>
  <div id="app">
    <img src="./assets/logo.png">
    <IntermediateButton
      :text="'Buttony'"
      :action="displaySecondButton"/>

    <TestButton
      v-if="secondButtonVisible"
      :text="'Second button'"
      :color="'green'"
      :action="doThings"/>
  </div>
</template>

<script>
  import IntermediateButton from './components/IntermediateButton.vue';
  import TestButton from './components/Button.vue';

  export default {
    name: 'app',
    components: {
      IntermediateButton, TestButton
    },
    data() {
      return {
        secondButtonVisible: false
      }
    },
    methods: {
      displaySecondButton() {
        console.log('First Button Clicked');
        this.secondButtonVisible = !this.secondButtonVisible;
      },
      doThings() {
        console.log('Second Button Clicked')
      }
    }
  };
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
