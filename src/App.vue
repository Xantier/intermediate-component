<template>
  <div id="app">
    <div>
      <h1>Dynamically bound</h1>
      <component
        :is="inter"
        v-bind="{
        text: 'Buttony',
        action: displaySecondButton
      }"
      />
      <component
        v-if="secondButtonVisible"
        :is="btn"
        v-bind="{
        text: 'Second button',
        action: doThings,
        color: 'green'
      }"
      />
    </div>
    <div>
      <h1>Hard coded dependency</h1>
      <IntermediateButton
        :text="'Buttony'"
        :action="displaySecondButton"/>

      <TestButton
        v-if="secondButtonVisible"
        :text="'Second button'"
        :color="'green'"
        :action="doThings"/>
    </div>
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
        secondButtonVisible: false,
        inter: IntermediateButton,
        btn: TestButton
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
