<template>
  <h2>List rendering</h2>
  <h3 v-for="name in names" :key='name'>{{ name }}</h3>
  <h3 v-for="(nam, index) in names" :key='index'>{{index}} {{ nam }}</h3>
  <h3 v-for="(fullName, index) in fullNames" :key='index'>{{fullName.first}} {{ fullName.last }}</h3>
  <div v-for="student in students" :key="student.name">
    <h2>{{ student.name }}</h2>
    <h3 v-for="additional in student.addData" :key="additional">{{ additional }}</h3>
  </div>
  <h2 v-for="(value,key,index) in nameInfo" :key="index">{{ key }} : {{value}}</h2>

  <template v-for="name in names" :key="name">
    <h2>{{name}}</h2>
  </template>

  <h1>conditional list rendering</h1>
  <template v-for="name in names" :key="name">
    <h2  v-if="name==='Nina'">{{ name }}</h2>
  </template>
</template>

<script>

export default {
  name: 'AppTwo',
  data() {
    return {
      names: ['Budi', 'Alias', "Nina"],
      fullNames: [
        { first: 'Budi', last:'Haryono'},
        { first: 'Alias', last:'Man'},
        { first: 'Nina', last:'Karlina'},
      ],
      students: [
        { name: 'Budi', addData:[10, 'Jakarta']},
        { name: 'Alias', addData:[11, 'Jakarta']},
        { name: 'Nina', addData:[9, 'Jakarta']},
      ],
      nameInfo : { first: 'Budi', last:'Haryono', father: 'Kaliri'}
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.danger {
  color: red;
}
.success {
  color: green;
}
</style>
