<template>
  <div class="person">
    <Person :person="persons" />
  </div>
</template>

<script>
import Person from "./Person.vue";
export default {
  name: "HelloWorld",
  data() {
    return {
      persons: null,
    };
  },
  components: {
    Person,
  },
  async created() {
    const resp = await fetch(
      "https://run.mocky.io/v3/86016330-8749-48d5-82f8-a9d08acddb50"
    );
    this.persons = await resp.json();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.person {
  margin: 20px;
  padding: 20px;
  border: 1px solid black;
}
</style>
