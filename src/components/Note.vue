<script setup lang="ts">
import {
  onBeforeMount,
  onMounted,
  onUpdated,
  reactive,
  ref,
  useTemplateRef,
  type Reactive,
  type Ref,
} from "vue";

const notes: Reactive<string[]> = reactive([]);
const note: Ref<string> = ref("");

const inputRef = useTemplateRef<HTMLInputElement>("inputNote");

const submitNote = () => {
  notes.push(note.value);
  note.value = "";
  inputRef.value?.focus();
};

onBeforeMount(() => {
  console.log("Component is about to mount...");
});

onMounted(() => {
  console.log("Component has been mounted.");
});

onUpdated(() => {
  console.log("Component has been updated.");
});
</script>

<template>
  <h1>Note Component</h1>
  <p>This is a simple note component.</p>

  <form>
    <label for="note">Enter a note:</label>
    <input type="text" id="note" v-model="note" ref="inputNote" />
    <button @click.prevent="submitNote">Submit</button>
  </form>

  <ul>
    <li v-for="(note, index) in notes" :key="index">
      {{ note }}
    </li>
  </ul>
</template>
