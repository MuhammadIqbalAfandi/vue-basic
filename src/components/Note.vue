<script setup lang="ts">
import { reactive, ref, useTemplateRef, type Reactive, type Ref } from "vue";

const notes: Reactive<string[]> = reactive([]);
const note: Ref<string> = ref("");

const inputRef = useTemplateRef<HTMLInputElement>("inputNote");

const submitNote = () => {
  notes.push(note.value);
  note.value = "";
  inputRef.value?.focus();
};
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
