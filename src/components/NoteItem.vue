<template>
  <base-container>
    <h1>{{ title }}</h1>
    <p>{{ note }}</p>
    <button @click="deleteNote">Delete Note</button>
  </base-container>
</template>

<script>
export default {
  emits: ['delete-note'],
  props: ['title', 'note'],
  methods: {
    deleteNote() {
      this.$emit('delete-note', this.title);
    },
  },
};
</script>
