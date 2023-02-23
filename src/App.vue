<template>
  <div>{{greet}} {{ content }}</div>
  <div v-text="vText"></div>
  <div v-html="vHtml"></div>
  <div v-bind:id="headingId">Heading</div>
  <button v-bind:disabled="isDisabled">BT Bind</button>
  <h2 class="underline">Underline</h2>
  <h2 v-bind:class="status">Binding Class</h2>
  <h2 class="underline" v-bind:class="status">Combine binding and static class</h2>
  <h2 v-bind:class="promoted && 'success'">Conditional binding</h2>
  <h2 v-bind:class="isRun?'success':'danger'">Result</h2>
  <h2 v-bind:class="['success', 'underline']">newly promoted</h2>
  <h2 v-bind:class="[promoted && 'success', isRun?'danger':'underline']">newly promoted</h2>
  <h2 v-bind:class="{
    promoted: promoted,
    new:isRun,
    'success':!isRun
  }">Object conditional</h2>
  <h2 v-bind:style="{
    color:primary, 
    fontSize:size + 'px', 
    'text-decoration': 'underline' 
    }">Binding inline style</h2>
  <h2 v-bind:style="headerStyle">Binding style</h2>
  <h2 v-bind:style="[headerStyle, successStyle]">Binding style</h2>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet : 'Hello',
      name: 'World!',
      vText: 'V-Text',
      vHtml: '<b>V-HTML</b>',
      headingId: 'heading',
      isDisabled: true,
      status: 'danger',
      promoted: true,
      isRun: false,
      primary: 'blue',
      size: 20,
      headerStyle: {
        fontSize: '20px',
        textDecoration: 'underline',
      },
      successStyle: {
        color: 'green',
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
