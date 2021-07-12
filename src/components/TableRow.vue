<template>
      <tr class="table__row" @click="viewUserInForm">
        <td class="table__row-cell">{{user.id}}</td>
        <td class="table__row-cell">{{user._foreigner}}</td>
        <td class="table__row-cell">{{user._name}}</td>
        <td class="table__row-cell">{{user._sex}}</td>
      </tr>
</template>
<script>
export default {
  name: "TableRow",
  props: ["user"],
  methods: {
      viewUserInForm() {
          this.$emit("viewUserInForm", this.user.id)
      }
  }
};
</script>
<style>
  .table__row {
    cursor: pointer;
  }
  .table__row-cell {
      background-color: #d8e6f3;
      border: 1px solid white
  }
</style>