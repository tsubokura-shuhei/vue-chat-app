<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!-- <Chat/> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
// import Chat from '@/components/Chat.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
    // Chat
  }
}
</script>
