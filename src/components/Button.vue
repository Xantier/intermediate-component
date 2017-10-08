<template>
  <button
    @click="action()"
    :style="{backgroundColor: color}"
    :text="text">
    {{ text }}
  </button>
</template>

<script>
  export default {
    name: 'TestButton',
    props: {
      action: {
        type: Function
      },
      text: {
        type: String
      },
      color: {
        type: String
      }
    },
  };
</script>
