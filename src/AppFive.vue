<template>
  <h1>Form Handling</h1>
  <div>
    <pre>
      {{ JSON.stringify(formValues,null,2) }}
    </pre>
  </div>
  <form @submit="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" name="name" id="name" v-model.trim="formValues.name">
    </div>

    <div>
      <label for="profile">Profile</label>
      <input type="text" name="profile" id="profile" v-model="formValues.profile">
    </div>

    <div>
      <label for="city">City</label>
      <select name="city" id="city" v-model="formValues.city">
        <option value="">Select city</option>
        <option value="jakarta">Jakarta</option>
        <option value="pekalongan">Pekalongan</option>
      </select>
    </div>

    <div>
      <label for="field">Field</label>
      <select name="field" id="field" multiple v-model="formValues.field">
        <option value="IT">IT</option>
        <option value="Health">Health</option>
        <option value="Sport">Sport</option>
      </select>
    </div>

    <div>
      <input type="checkbox" name="remoteWork" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
      <label for="remoteWork">Open to remote work</label>
    </div>




    <div>
      <button>Submit</button>
    </div>

  </form>
</template>

<script>

export default {
  name: 'AppFive',
  data() {
    return {
      formValues: {
        name: '',
        profile: '',
        city: '',
        field: [],
        remoteWork: 'no',
      }
    }
  },
  methods: {
    submitForm(event) {
      event.preventDefault();
      console.log(this.formValues);
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
