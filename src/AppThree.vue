<template>
    <!-- put function into html  -->
    <h1>Method</h1>
    <h2>{{ 2 + 3 }}</h2>
    <h2>add method = {{ add(2, 5, 10) }}</h2>
    <h2>multiply method = {{ multiply(10) }}</h2>
    <h2>multiply method = {{ multiply(baseValue) }}</h2>
</template>

<script>
export default {
    name: "AppThree",
    data() {
        return {
            baseMultiplier: 5,
            baseValue: 2,
        };
    },
    methods: {
        add(a, b, c) {
            return a + b + c;
        },
        multiply(num) {
            return num * this.baseMultiplier;
        },
    },
};
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
