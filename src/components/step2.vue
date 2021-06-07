<template>
  <div class="root">
    <div style="padding-left: 200px; padding-top: 50px">
      <br>
      <h2>I will find you!</h2>
      <input type="text">
      <p>Total names: {{ this.users.length }}. Coincidence: {{ }}</p>

      <p
          style="color: gray;"
          v-for="(value, key) in users"
          v-bind:key="key"
      >
        {{ value.firstName }}
      </p>

    </div>
    <br> <br> <br>
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
          v-for="(value, index) in users"
          v-bind:key="index">
        {{ `${index + 1} ${getFullName(value)}` }}
      </li>
    </ul>
    <button
        type="button"
        v-on:click="currentPage--"
    >
      previous
    </button>
    <button
        v-for="page in pages"
        :key="page"
        type="button"
        v-on:click="currentPage = page"
    >
      {{ page }}
    </button>
    <button
        type="button"
        v-on:click="currentPage++"
    >
      next
    </button>
    <p>Page {{ currentPage }} of {{ pages }}</p>
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
        {
          firstName: 'Maxim',
          secondName: 'Andreevich',
          lastName: 'Polshkov',
        }
      ],
      pages: 3,
      currentPage: 1,
    }
  },
  // computed свойства в отличие от methods будут высчитаны только один раз, но не можем передавать переменные
  computed: {
    getAuthorFullName() {
      return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
    },
    searchName() {
      return 1;
    },

  },
  methods: {
    getFullName(users) {
      console.log(this.users.includes('Ivan', 0));
      return `${users.firstName} ${users.secondName} ${users.lastName}`

    },
    loadUsers(page) {
      console.log(`Load users: page ${page}`)
    }
  },
  //watcher-ы следят за свойствами, принимает 2 аргумента, новое и старое
  watch: {
    currentPage(page) {
      this.loadUsers(page)
    }
  }
}
</script>

<style lang="scss">

</style>