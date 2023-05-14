<template>
    <!-- event listener  -->
    <h2>{{ name }}</h2>
    <!-- onclick and mouse over  -->
    <div>
        <button v-on:click="name = 'Nina'">Change Name</button>
        <button v-on:mouseover="name = 'Ali'">Change Name</button>
    </div>

    <!-- complete syntax  -->
    <h2>{{ count }}</h2>
    <button v-on:click="decrement">Minus</button>
    <button v-on:click="increment">Plus</button>
    <button v-on:click="reset">reset</button>

    <!-- shorthand  -->
    <h2>{{ count }}</h2>
    <button @click="decrement">Minus</button>
    <button @click="increment">Plus</button>
    <button @click="reset">reset</button>

    <h2>{{ name2 }}</h2>
    <div>
        <button @click="changeName">Change Name</button>
    </div>

    <!-- get event  -->
    <button @click="loggerEvent">See Event</button>
</template>

<script>
export default {
    name: "AppFour",
    data() {
        return {
            name: "Budi",
            name2: "Budi",
            count: 0,
        };
    },
    methods: {
        reset() {
            this.count = 0;
        },
        increment() {
            this.count += 1;
        },
        decrement() {
            this.count -= 1;
        },
        changeName() {
            this.name = "Munir";
        },
        loggerEvent(event) {
            console.log(event);
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
