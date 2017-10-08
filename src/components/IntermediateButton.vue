<template>
  <test-button
    :action="doIntermediateAction"
    :color="colour"
    :text="text"/>
</template>

<script>

  import TestButton from './Button.vue';

  export default {
    name: 'IntermediateButton',
    components: {TestButton},
    props: {
      action: {
        type: Function
      },
      text: {
        type: String
      }
    },
    data() {
      return {
        colour: 'blue'
      }
    },
    methods: {
      doIntermediateAction() {
        console.log('Intermediate');
        this.colour = this.colour === 'red' ? 'blue' : 'red';
        this.action();
      }
    }
  };
</script>
