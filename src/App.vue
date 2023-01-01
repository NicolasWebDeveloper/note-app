<template>
  <h1>Take a Note</h1>
  <addNote @add-note="addNote"></addNote>
  <note-item v-for="note in notes" :title="note.title" :note="note.note" :key="note.title" @delete-note="deleteNote"></note-item>
</template>

<script>
import addNote from './components/AddNote.vue';
import noteItem from './components/NoteItem.vue';
export default {
  data() {
    return {
      notes: [{ title: 'Test', note: 'hello' }],
    };
  },
  components: {
    addNote,
    noteItem,
  },
  methods: {
    addNote(title, note) {
      this.notes.push({ title, note });
    },
    deleteNote(title) {
      console.log(title);
      this.notes = this.notes.filter(note => note.title !== title);
    },
  },
};
</script>

<style>
* {
  font-family: sans-serif;
}

body {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
</style>
