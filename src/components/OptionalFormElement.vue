<template>
  <div class="component">
    <p class="component__name">
      {{element.ns}}
    </p>
    <input
      v-if="this.type == 1"
      v-bind:style="'width: ' + elementWidth + 'px;'"
      v-bind:type="elementType()"
      v-bind:value="user[element.rv]"
    >
    <input
      v-if="this.type == 3"
      v-bind:type="elementType()"
      v-model="checkedFunc"
    >
    <select
      v-if="this.type == 2"
      v-bind:style="'width: ' + elementWidth + 'px;'"
      v-model="selectedFunc"
    >
      <option
        v-for="v in element.sl"
        :key="v.id"
      >{{v.name}}</option>
    </select>
  </div>
</template>
<script>
export default {
  name: "OptionalFormElement",
  props: ["element", "type", "width", "user", "rv", "foreigner", "sex"],
  computed: {
    elementWidth: function () {
      return this.width;
    },
    checkedFunc: {
      get(){
        return this.foreigner
      }
    },
    selectedFunc: {
      get() {
        return this.sex == "1" ?  'муж' :  'жен'
      }
    }
  },
  methods: {
    elementType: function() {
      if (this.type == 1) {
        return 'text'
      }
      if (this.type == 3) {
        return 'checkbox'
      }
    },
  }
};
</script>
<style>
  .component {
    display: flex;
    margin-bottom: 10px;
  }
  .component:not(:last-child) {
    margin-bottom: 10px;
  }
  .component__name {
    margin: 0 20px 0 0;
  }
</style>