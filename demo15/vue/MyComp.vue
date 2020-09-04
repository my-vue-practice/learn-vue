<template>
  <div class="component">
    <h3>自定义comp组件</h3>
    <p>初始值：{{ v }}</p>
    <button @click="minus">减1</button>
    <button @click="add">加1</button>
  </div>
</template>

<script>
export default {
  // event 自定义为 change，也可以不声明model，直接用默认的input事件this.$emit('input', value);
  model: {
    prop: 'value',
    event: 'change',
  },
  props: {
    value: {
      type: Number,
      default: 0,
    },
  },
  mounted() {
    console.log('[value]', this.value);
  },
  computed: {
    v() {
      return this.value;
    },
  },
  methods: {
    minus() {
      this.$emit('change', this.value - 1);
    },
    add() {
      this.$emit('change', this.value + 1);
    },
  },
};
</script>

<style scoped>
.component {
  padding: 15px;
  border: 2px dashed yellowgreen;
  background-color: lemonchiffon;
}
</style>
