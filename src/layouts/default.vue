<template>
  <v-app>
    <!-- ALERT -->
    <Alert v-if="alertStore.showAlert" />
    <View></View>
  </v-app>
</template>

<script setup>
import View from "./view.vue";
import Alert from "@/components/shared/Alert.vue";
import { useAlertStore } from "@/stores/alert";

const alertStore = useAlertStore();
</script>
