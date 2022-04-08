<template>
  <input type="name" v-model="answer" />
  <div>
    <button v-on:click="save_input(1)">1</button>
    <button v-on:click="save_input(2)">2</button>
    <button v-on:click="save_input(3)">3</button>
    <button v-on:click="method_select(plus)">+</button>
  </div>
  <div>
    <button v-on:click="save_input(4)">4</button>
    <button v-on:click="save_input(5)">5</button>
    <button v-on:click="save_input(6)">6</button>
    <button v-on:click="method_select(minus)">-</button>
  </div>
  <div>
    <button v-on:click="save_input(7)">7</button>
    <button v-on:click="save_input(8)">8</button>
    <button v-on:click="save_input(9)">9</button>
    <button v-on:click="method_select(divide)">/</button>
  </div>
  <div>
    <button v-on:click="save_input(0)">0</button>
    <button v-on:click="clear_input()">Clear</button>
    <button v-on:click="method_select(multiply)">*</button>
  </div>
  <div><button v-on:click="calculation()">Enter</button></div>
</template>

<script>
export default {
  data: function () {
    return {
      method_selected: false,
      first_number: "",
      second_number: "",
      answer: "",
      method: "",
      plus: "+",
      minus: "-",
      multiply: "*",
      divide: "/",
    };
  },
  methods: {
    clear_input: function () {
      this.answer = "";
      this.method_selected = false;
      this.first_number = "";
      this.second_number = "";
    },
    method_select: function (method) {
      this.method_selected = true;
      this.method = method;
    },
    save_input: function (number) {
      if (this.method_selected == false) {
        this.first_number = this.answer + number;
        this.answer = this.first_number;
      }
      if (this.method_selected == true) {
        this.answer = this.second_number;
        this.second_number = this.answer + number;
        this.answer = this.second_number;
      }
    },
    calculation: function () {
      if (this.method == "+") {
        this.answer = parseInt(this.first_number) + parseInt(this.second_number);
      }
    },
  },
};
</script>
