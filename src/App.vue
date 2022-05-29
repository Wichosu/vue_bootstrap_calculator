<script>
export default {
  data() {
    return {
      display: '0',
      input: '',
      add: (a, b) => a + b,
      substract: (a, b) => a - b,
      multiply: (a, b) => a * b,
      divide: (a, b) => a / b,
      first: /\d+\*\d+/
    }
  },
  methods: {
    compute(){
      this.input = this.first.exec(this.input)
      alert(this.input)
    },
    writeInput(char){
      this.input += char
    },
    clean(){
      this.input = ''
      this.display = '0'
    },
  }

}
</script>

<template>
  <H1 class="container border center">Calculator</H1>

  <p class="container border center">{{ display }}</p>
  <div class="center">
    <input class="center" v-model="input"> 
  </div>
  <div class="container center">
    <div class="row">
      </div>
    <div class="row">
      <button class="col btn btn-danger" @click="clean">Clean</button>
      <button class="col btn btn-primary" @click="alert">Alert</button>
      <button class="col btn btn-success" @click="compute">=</button>
      <button class="col btn btn-secondary" @click="writeInput('/')">/</button>
    </div>
    <div class="row">
      <button class="col btn btn-secondary" @click="writeInput('7')">7</button>
      <button class="col btn btn-secondary" @click="writeInput('8')">8</button>
      <button class="col btn btn-secondary" @click="writeInput('9')">9</button>
      <button class="col btn btn-warning" @click="writeInput('+')">+</button>
    </div>
    <div class="row">
      <button class="col btn btn-secondary" @click="writeInput('4')">4</button>
      <button class="col btn btn-secondary" @click="writeInput('5')">5</button>
      <button class="col btn btn-secondary" @click="writeInput('6')">6</button>
      <button class="col btn btn-warning" @click="writeInput('-')">-</button>
    </div>
    <div class="row">
      <button class="col btn btn-secondary" @click="writeInput('1')">1</button>
      <button class="col btn btn-secondary" @click="writeInput('2')">2</button>
      <button class="col btn btn-secondary" @click="writeInput('3')">3</button>
      <button class="col btn btn-warning" @click="writeInput('*')">*</button>
    </div>
    <div class="row">
      <button class="col btn btn-secondary" @click="writeInput('0')">0</button>
    </div>
  </div>
</template>

<style>
.center{
  text-align: center;
}
.btn{
  margin: 0.1em;
}
</style>