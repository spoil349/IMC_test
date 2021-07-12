<template>
    <div class="container">
      <p>Форма</p>
      <OptionalFormElement
        v-for="element in forms"
        :key="element.id"
        :element = element
        :type = element.ct
        :width = element.cw
        :rv = element.rv
        :user = user
        :foreigner = user._foreigner
        :sex = user._sex
      />
    </div>
    
</template>
<script>
import OptionalFormElement from "@/components/OptionalFormElement";

export default {
  name: "FormData",
  components: {
    OptionalFormElement,
  },
  props: ["user"],
  data() {
    return {
      forms: []
    }
  },
  methods: {},
  async mounted() {
    const res = await fetch(
      'http://localhost:3000/formData'
    );
    const forms = await res.json();
    this.forms = forms.sort((a, b) => a.age > b.age ? 1 : -1);
  },
};
</script>
<style>
  .container {
    display: flex;
    flex-direction: column;
    border: 1px solid black;
    border-radius: 10px;
    padding: 30px;
  }
</style>