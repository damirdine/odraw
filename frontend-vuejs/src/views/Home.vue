<template>
  <main v-if="isConnected">
    <DrawWorkspace :socket="socket" class="workspace" />
    <Chat :socket="socket" class="chat" />
  </main>
  <div v-else class="loader-container">
    <div class="loader-message">
      <div class="spinner"></div>
      <p>Veuillez patienter, les serveurs sont en cours de démarrage...</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue";
import { socket } from "@/services";

import Chat from "../components/Chat.vue";
import DrawWorkspace from "../components/DrawWorkspace.vue";

export default defineComponent({
  components: {
    Chat,
    DrawWorkspace
  },
  setup() {
    const isConnected = ref(false);

    onMounted(() => {
      if (socket.connected) {
        isConnected.value = true;
      } else {
        socket.on("connect", () => {
          isConnected.value = true;
        });
      }
    });

    return {
      socket,
      isConnected
    };
  }
});
</script>

<style scoped>
main {
  display: flex;
  height: calc(100vh - var(--nav-height));
}

.workspace {
  width: calc(100vw - var(--chat-width));
  border-right: 1px solid var(--color-secondary);
}

.chat {
  width: var(--chat-width);
}

.loader-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: calc(100vh - var(--nav-height));
  background-color: #f9f9f9;
  color: #333;
  text-align: center;
  font-family: sans-serif;
}

.loader-message {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.spinner {
  border: 6px solid #e0e0e0;
  border-top: 6px solid #3498db;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  animation: spin 1s linear infinite;
  margin-bottom: 1rem;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>
