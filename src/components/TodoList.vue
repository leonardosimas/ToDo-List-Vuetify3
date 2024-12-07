<template>
  <div>
    <v-text-field
      clearable
      @keyup.enter="taskStore.addTask"
      label="Adicione uma tarefa"
      :rules="rules"
      v-model="taskStore.titleTaskCreating"
    >
    </v-text-field>

    <ListTasks />
  </div>
</template>

<script setup>
import { onMounted } from "vue";

import ListTasks from "./ListTasks.vue";

import { useTaskStore } from "@/stores/task";

const taskStore = useTaskStore();

const rules = [
  (value) => {
    if (!value || value.length >= 5) return true;

    return "O título de sua tarefa tem que ter 5 caracteres ou mais.";
  },
];

onMounted(() => {
  taskStore.getTasks();
});
</script>