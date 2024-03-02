<template>
  <Navbar :changeNavFlag="changeNavFlag" :navFlag="this.navFlag"/>
  <Home v-show="navFlag == 1"/>
  <MainEvent v-show="navFlag == 2"/>
  <Union v-show="navFlag == 3" />
  <Chat_Closed v-show="chatFlag == 1" :changeChatFlag="changeChatFlag" :chatFlag="this.chatFlag"/>
  <Chat v-show="chatFlag == 2" :changeChatFlag="changeChatFlag" :chatFlag="this.chatFlag"/>
</template>


<script>
import Navbar from './components/NavBar.vue'
import Chat from './components/Chat.vue'
import Home from './components/Home.vue'
import MainEvent from './components/MainEvent.vue'
import Union from './components/Union.vue'
import Chat_Closed from './components/Chat_Closed.vue'

export default {
  components: {Navbar, Chat, Home, MainEvent, Union, Chat_Closed},
  data() {
    return {
      navFlag: 1,
      chatFlag: 1,
      activeteFlag: false
    }
  },
  methods: {
    changeNavFlag(val) {
      this.navFlag = val
    },
    changeChatFlag(val) {
      this.chatFlag = val
    }
  }
}
</script>

<style scoped>
.app {
  display: flex;
  flex-direction: row;
}
</style>
