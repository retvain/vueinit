<template>
  <div class="root">
    <h1>How to gain 100$ in hour???</h1>
    <div class="main-information">
      <img src="http://placekitten.com/g/400/200">
      <div class="info">
        <h2>
          {{ getAuthorFullName }}
        </h2>
        <strong>business - couch</strong>
        <ul>
          <li>Learn people make real money</li>
          <li>I know, what you need.</li>
          <li>Never lie!</li>
        </ul>
      </div>
    </div>
    <p>participant: {{ users.length }}</p>
    <ul>
      <li
          v-for="(users, index) in users"
          v-bind:key="index">
        {{ `${index+1} ${getFullName(users)}` }}
      </li>
    </ul>
    <!--  <input type="text" @input="firstName = $event.target.value">-->
  </div>
</template>

<script>
export default {
  name: "step2.vue",
  data() {
    return {
      firstName: 'Mikhail',
      secondName: 'Petrovich',
      lastName: 'Ivanov',
      users: [
        {
          firstName: 'Ivan',
          secondName: 'Sergeevich',
          lastName: 'Petrov',
        },
        {
          firstName: 'John',
          secondName: 'Mikhailovich',
          lastName: 'Davydov',
        },
        {
          firstName: 'Sergei',
          secondName: 'Viktorovich',
          lastName: 'Petryakov',
        },
      ]
    }
  },
  // computed свойства в отличие от methods будут высчитаны только один раз, но не можем передавать переменные
  computed: {
    getAuthorFullName() {
      return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
    }
  },
  methods: {
    getFullName(users) {
      return `${users.firstName} ${users.secondName} ${users.lastName}`
    }
  }
}
</script>

<style lang="scss">

</style>