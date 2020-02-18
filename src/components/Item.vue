<template>
  <p>
    <span style="color:red">{{ item.id + 1 }}</span
    >{{ item.value + item.value }}
  </p>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
p {
  width: 100%;

  span {
    margin-right: 5px;
  }
}
</style>
