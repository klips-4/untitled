<template src="./template.html">

</template>

<script>
import AddFormRoom from "@/components/AddFormRoom/AddFormRoom";
import ChatRegistry from "@/components/ChatRegistry/ChatRegistry";
import RegistryRoom from "@/components/RegistryRoom/RegistryRoom";

export default {
  name: "ControllerRoom",
  components: {
    AddFormRoom,
    ChatRegistry,
    RegistryRoom
  },
  data() {
    return {
      formVisible: false,
      rooms: [],
      chatData: null,
      currentRoom: null
    }
  },
  methods: {
    formVisibleChange() {
      this.formVisible = !this.formVisible
    },
    openRoom(idRoom) {
      this.chatData = this.rooms[idRoom];
      this.currentRoom = idRoom;

    },
    closeChat() {
      this.chatData = null;
      this.currentRoom = null;
    },
    addRoomInRooms(roomsData) {
      const room = {...roomsData, id: this.rooms.length}
      this.rooms.push(room)
    },
    addMessage(message) {
      this.rooms[this.currentRoom].message.push(message);
    }
  }
}
</script>

<style scoped src="./style.less" lang="less">

</style>