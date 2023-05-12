<template>
  <tr class="table-item__table-row">
    <td>{{ title }}</td>
    <td>{{ isbn }}</td>
    <td>
      <BaseButton
        text=""
        variant="primary"
        @button-event="clickBookmarkButton"
      />
    </td>
  </tr>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  components: {
    BaseButton,
  },
  props: {
    title: { type: String },
    isbn: { type: String },
  },
  data() {
    return {
      isBookmarked: false,
    };
  },
  methods: {
    // changeBtnText() {
    //   {
    //     this.isBookmarked ? "Remove Bookmark" : "Add Bookmark";
    //   }
    clickBookmarkButton() {
      this.isBookmarked = !this.isBookmarked;
      console.log(this.isBookmarked);
      // this.$emit("bookmarkClicked", this.isbn);
    },
  },
};
// emits: ["butbookmarkClicked"],
</script>

<style>
.table-item__table td {
  padding: 12px 15px;
}
</style>
