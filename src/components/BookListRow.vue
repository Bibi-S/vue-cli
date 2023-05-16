<template>
  <tr class="table-item__table-row">
    <td>{{ title }}</td>
    <td>{{ isbn }}</td>
    <td>
      <BaseButton
        :text="buttonText"
        variant="primary"
        @button-event="clickBookmarkButton"
      />
    </td>
  </tr>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  emits: ["bookmark-button-click"],
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
    clickBookmarkButton() {
      this.isBookmarked = !this.isBookmarked;
      this.$emit("bookmark-button-click");
      console.log(this.isBookmarked);
    },
  },
  computed: {
    buttonText() {
      if (this.isBookmarked) {
        return "Remove Bookmark";
      } else {
        return "Add Bookmark";
      }
    },
  },
};
</script>

<style>
.table-item__table td {
  padding: 12px 15px;
}
</style>
