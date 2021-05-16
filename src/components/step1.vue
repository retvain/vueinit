<template>
  <div class="root">
    <div><label>
      Insert email:
      <input
          type="email"
          v-bind:value="email"
          v-on:input="emailInput($event.target.value)"
      />
    </label>
      <label>
        Insert password:
        <input
            type="password"
            v-bind:value="password"
            v-on:input="passwordInput($event.target.value)"
        />
      </label>
      <br><br>
      email: {{ email }}
      password: {{ password }}
    </div>
    <br>
    <div>

      <button id="less" v-on:click="decreaseCounter">-</button>
      <input style="width: 3em" type="number" v-bind:value="counter">
      <button id="'more" v-on:click="increaseCounter">+</button>

    </div>
  </div>

</template>

<script>
export default {
  name: "step1.vue",

  data() {
    return {
      email: 'example@mail.com',
      password: '12345678',
      counter: 9

    }
  },
  methods: {
    emailInput(value) {
      this.email = value
    },
    passwordInput(value) {
      this.password = value
    },
    increaseCounter() {
      if ((0 <= this.counter) && (this.counter < 10)) {
        this.counter++
      }
    },
    decreaseCounter() {
      if ((0 < this.counter) && (this.counter <= 10)) {
        this.counter--
      }

    }
  }
}
</script>
