<template>
  <base-container>
    <template #default>
      <form @submit.prevent="addNote">
        <label>Title</label>
        <input type="text" v-model="currentTitle" />
        <label>Note</label>
        <input type="text" v-model="currentNote" />
        <button type="submit">Add Note</button>
      </form>
    </template>
  </base-container>
</template>

<script>
export default {
  emits: ['add-note'],
  data() {
    return {
      currentTitle: '',
      currentNote: '',
    };
  },
  methods: {
    addNote() {
      this.$emit('add-note', this.currentTitle, this.currentNote);
      this.currentTitle = '';
      this.currentNote = '';
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  justify-content: center;

  width: 15rem;
}
</style>
