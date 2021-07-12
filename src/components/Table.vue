<template>
    <table class="table">
      <tr class="table__row">
        <th class="table__row-header">Идентификатор</th>
        <th class="table__row-header">Иностранец</th>
        <th class="table__row-header">Имя</th>
        <th class="table__row-header">Пол</th>
      </tr>
      <TableRow 
        v-for="user in users"
        :key="user.id"
        :user = user
        @viewUserInForm = "viewUserInForm"
      />
    </table>
</template>
<script>
import TableRow from "@/components/TableRow";
import _ from "lodash";

export default {
  name: "Table",
  components: {
    TableRow
  },
  data() {
    return {
      users: []
    }
  },
  methods: {
      viewUserInForm(id) {
          let userToView = _.find(this.users, {id:id})
          this.$emit("viewUserInForm", userToView);
      }
  },
  async mounted() {
    const res = await fetch(
      'http://localhost:3000/table'
    );
    const users = await res.json();
    this.users = users;
  }

};
</script>
<style>
  .table {
    font-size: 14px;
    border-collapse: collapse;
  }
  .table__row-header {
    background-color: #afcde7;
    color: #fff;
    padding: 10px 20px;
    border: 1px solid white
  }
</style>