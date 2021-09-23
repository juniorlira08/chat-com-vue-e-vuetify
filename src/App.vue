<template>
  <v-app>
    <v-main>
      <v-app-bar color="green">{{ firstName }}</v-app-bar>
      <div class="menssages-container">
        <div v-for="(message, index) in messages" :key="index">
          <message-card :messageProp="message" />
        </div>
      </div>
      <bottom-bar @send-message="addMessage($event)" />
    </v-main>
  </v-app>
</template>

<script>
  import MessageCard from './components/MessageCard.vue'
  import BottomBar from './components/BottomBar.vue'
  export default {
    components : {
      MessageCard,
      BottomBar
    },
    data() {
      return {
        nome: "Roberto Silva",
        messages: [
          {
            name: "Roberto Silva",
            text: "Olá"
          },
          {
            name: "Roberto Silva",
            text: "Tudo bem?"
          }
        ],
      }
    },
    computed : {
      firstName() {
        console.log('nhanha')
        return this.nome.split(' ')[0]
      }
    },
    methods: {
      addMessage(event) {
        console.log(event)
        this.messages.push(event)
      }
    }
  }
</script>