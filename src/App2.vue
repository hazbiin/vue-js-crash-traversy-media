<script>
  export default {
    data() {
      return {
        name: "John Doe",
        boolStatus: true,
        status: "pending",
        tasks: ['Task One', 'Task Two', 'Task Three'],
        link: 'https://google.com'
      }
    },
    methods: {
      toggleStatus() {
        if(this.status === "active") {
          this.status = 'pending';
        }else if(this.status === 'pending') {
          this.status = 'inactive';
        }else {
          this.status ='active'
        }
      }
    }
  }

</script>

<template>
  <h1>{{ name }}</h1>
  <h2 v-if=boolStatus>rendered by boolean data</h2>

  <p v-if="status === 'active' ">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task"> {{ task }}</li>
  </ul>

  <!-- <a v-bind:href="link">Click for Google</a> -->
  <a :href="link">Click for Google</a>
  <br/>
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>


<style scoped>
h1{
  color: red;
}
</style>
