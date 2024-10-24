<script setup>
import { ref, onMounted } from "vue";
import ChatMessages from "./ChatMessages.vue";
import ChatForm from "./ChatForm.vue";

const messages = ref([]);

onMounted(() => {
  const savedMessages = localStorage.getItem("chatMessages");
  if (savedMessages) {
    messages.value = JSON.parse(savedMessages);
  }
});

function addMessage(newMessage) {
  messages.value.push(newMessage);
  // Sla de berichten op in localStorage
  localStorage.setItem("chatMessages", JSON.stringify(messages.value));
}
</script>

<template>
  <ChatMessages :messages="messages" />
  <ChatForm @sendMessage="addMessage" />
</template>

<style scoped></style>
