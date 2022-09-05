<template>
  <div v-if="person != null">
    <div class="person">
      <h1>{{ person.name }}</h1>
      <p>{{ person.gender }}</p>
      <div v-if="person?.drs?.length !== 0">
        <PersonComponent
          v-for="emp in person?.drs"
          :key="emp.id"
          :person="returnPerson(emp)"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PersonComponent",
  methods: {
    returnPerson(person) {
      return person;
    },
  },
  created() {
    console.log(this.person);
  },
  props: ["person"],
};
</script>