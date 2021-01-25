<template>
  <div>
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    quote: {
      type: String,
      default: '',
    },
  },
}
</script>
<style scoped>
div {
  width: 30%;
  border: 1px solid #eee;
  min-height: 200px;
  border-radius: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  margin: 1.5%;
}
div:hover {
  background-color: #efefef;
}
</style>
