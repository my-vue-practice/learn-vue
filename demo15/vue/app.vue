<template>
  <div id="root">
    <h3>v-model在非表单input组件应用</h3>
    <my-comp v-model="compValue1"></my-comp>
    <p>父组件：{{ compValue1 }}</p>
    <br />
    <my-comp v-model="compValue2"></my-comp>
    <p>父组件：{{ compValue2 }}</p>
  </div>
</template>

<script>
import MyComp from './MyComp';
export default {
  components: {
    MyComp,
  },
  data() {
    return {
      compValue1: 10,
      compValue2: 0,
    };
  },
};
</script>

<style scoped></style>
