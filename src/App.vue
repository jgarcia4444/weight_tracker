<template>
  <div id="app" class="text-center">
    <!--nav bar showing the name of the web app clicking the name redirects to same page-->
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
      <a class="navbar-brand" href="/">Jake's Weight Tracker</a>
    </nav>
    <div class="container mt-5">
      <form @submit.prevent="addWeight()">
        <div class="form-group row">
          <div class="col-sm-6 has-success">
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
    <Graph1 />
  </div>
</template>

<script>
import Graph1 from './components/createGraph.vue';

export default {
  name: 'app',
  components: {
    Graph1
  },
  data() {
    return {
      // users array, newWeight, 
      users: [
        { user: 'Jake', weight: [] },
        { user: 'Andrea', weight: [] },
      ],
      newWeight: 0,
      inputName: '',
      wrongName: false,
    };
  },

  // watch the users array for changes
  watch: {
    users: {
      handler() {
        localStorage.users = JSON.stringify(this.users);
      },
      deep: true
    }
  },

  // load the data from localStorage
  mounted() {
    if (localStorage.users) {
      this.users = JSON.parse(localStorage.users);
    };
  },

  methods: {
    // push the user name with new weight input into the users array as an // object
    addWeight() {
      // Checks which user to add the weight to
      if (this.inputName === 'Jake') {
        this.users[0].weight.push(this.newWeight);
        this.wrongName = false;
        this.inputName = '';
        this.newWeight = 0;
      } else if (this.inputName === 'Andrea') {
        this.users[1].weight.push(this.newWeight);
        this.wrongName = false;
        this.inputName = '';
        this.newWeight = 0;
      } else {
        this.wrongName = true;
        const err = new Error('Name does not match');
        throw(err);
      }
    },
  },
};
</script>

<style>

</style>
