<template>
  <h1>Computed Properties</h1>
  <h2>fullname - {{ firstName }} {{ lastName }}</h2>
  <h2>computed name - {{ fullName }}</h2>
  <button @click="products.push({name:'TV', price:2500})">Add Item</button>
  <h2>computed total - {{ total }}</h2>
  <h2>method total - {{ getTotal() }}</h2>
  <h2 v-for="{name, index} in expensive" :key="index">{{name}}</h2>
  <button @click="changeFullName()">Change name</button>
</template>

<script>

export default {
  name: 'AppSix',
  data() {
    return {
      firstName: 'Ali',
      lastName: "Buni",
      products: [
        {
          name: 'Hp',
          price: 2000,
        },
        {
          name: 'Laptop',
          price: 4000,
        },
        {
          name: 'Computer',
          price: 7000,
        },
      ]
    }
  },
  methods: {
    getTotal() {
      return this.products.reduce((total, curr) => (total = total + curr.price), 0);
    },
    changeFullName() {
      this.names='Bambang Wijaya'
    }
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    },
    total() {
      return this.products.reduce((total, curr) => (total = total + curr.price), 0);
    },
    expensive() {
      return this.products.filter(product=>product.price > 3000)
    },
    names: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const comName = value.split(' ');
        this.firstName = comName[0];
        this.lastName = comName[1];
        
      }
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

</style>
