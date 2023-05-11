<template>
  <tr class="table-item__table-row">
    <td>{{ title }}</td>
    <td>{{ isbn }}</td>
    <td>
      <BaseButton text="changeBtnText" variant="primary" @clickedBtn="" />
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
    isBookmarked: { type: Boolean },
  },
  methods: {
    changeBtnText() {
      return {
     isBookmarked ? "Remove Bookmark" : "Add Bookmark";
      },
    },
  },
};
</script>

<style>
.table-item__table td {
  padding: 12px 15px;
}
</style>
