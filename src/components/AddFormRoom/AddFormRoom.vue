<template src="./template.html">

</template>

<script>


export default {
  name: "AddFormRoom",
  beforeMount() {
    this.roomData = {...this.defaultRoomData};
  },
  props: [],

  data() {
    return {
      defaultRoomData: {name:''},
      roomData: null
    }
  },
  methods: {
    closeDialog() {
      this.roomData = null;
      this.$emit('close')
    },
    closeAddRoom() {
      this.$emit('closeAddRoom')
    },
    addRoom() {
      this.$emit('addRoom', this.roomData);
      this.closeDialog();
    }
  }

}

</script>

<style scoped src="./style.less" lang="less">

</style>