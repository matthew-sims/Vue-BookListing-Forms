<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input type="checkbox" v-model="bookData.finishedReading">
      <label for="borrowed">borrowed</label>
      <input type="radio" value="borrowed" v-model="bookData.ownership">
      <label for="bought">bought</label>
      <input type="radio" value="bought" v-model="bookData.ownership">
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookTitle: "",
      bookAuthor: "",
      bookData: {
        bookTitle: '',
        bookAuthor: '',
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
