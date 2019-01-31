<template>
  <div id="app" class="text-center">
    <!--nav bar showing the name of the web app clicking the name redirects to same page-->
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <a class="navbar-brand" href="/">Jake's Weight Tracker</a>
    </nav>
    <div class="container mt-5">
      <form @submit.prevent="addWeight()">
        <div class="form-group row">
          <div class="col-sm-6">
            <label for="name">Name:</label>
            <input v-model="inputName" class="form-control" type="text" id="name" required/>
          </div>
          <div class="col-sm-6">
            <label for="weight">Weight</label>
            <input v-model="newWeight" class="form-control" type="number" id="weight" required/>
            <small id="weight">(lbs)</small>
          </div>
        </div>
        <button class="btn btn-primary" type="submit">Add weight</button>
      </form>
    </div>
  </div>
</template>

<script>


export default {
  name: 'app',
  data() {
    return {
      // users array, newWeight, 
      users: [
        {user: 'Jake', weight: [],},
        // {name: 'Andrea', weight: [],}
      ],
      newWeight: 0,
      inputName: '',
    }
  },
  methods: {
    // push the user name with new weight input into the users array as an // object
    addWeight() {
      if (this.inputName == 'Jake') {
        this.users[0].weight.push(this.newWeight);
      } else {
        console.log('Hello World')
      }
    },
  }
};
</script>

<style>

</style>
