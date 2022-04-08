<template>
  <input type="number" v-model="answer" />
  <div>
    <button v-on:click="answer = 1">1</button>
    <button v-on:click="answer = 2">2</button>
    <button v-on:click="answer = 3">3</button>
    <button>+</button>
  </div>
  <div>
    <button v-on:click="answer = 4">4</button>
    <button v-on:click="answer = 5">5</button>
    <button v-on:click="answer = 6">6</button>
    <button>-</button>
  </div>
  <div>
    <button v-on:click="answer = 7">7</button>
    <button v-on:click="answer = 8">8</button>
    <button v-on:click="answer = 9">9</button>
    <button>/</button>
  </div>
  <div>
    <button v-on:click="answer = 0">0</button>
    <button>Clear</button>
    <button>*</button>
  </div>
  <div><button>Enter</button></div>
</template>

<script>
export default {
  data: function () {
    return {
      enter: false,
      answer: 0,
      numbers: [],
      method: "",
    };
  },
  methods: {
    clear_input: function () {
      this.numbers = [];
      this.answer = 0;
    },
    save_input: function (number) {
      this.numbers.push(number);
      if (this.enter == true) {
        this.calculation();
        this.enter == false;
      }
    },
    calculation: function () {},
  },
};
</script>
