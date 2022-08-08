<template src="./template.html">

</template>

<script>
export default {
  name: "RegistryRoom",
  props: ['rooms'],
  methods: {
    clickItem(id) {
      this.$emit('openRoom', id);
    }
  }
}
</script>

<style scoped src="./style.less" lang="less">

</style>