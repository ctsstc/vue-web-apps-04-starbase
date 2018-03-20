<template>
  <div id="app">
    <h2>{{title}}</h2>
    <button class="btn btn-primary" @click="fetchCharacter">Test Fetch Characters</button>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team"
    };
  },
  methods: {
    fetchCharacter() {
      fetch("https://swapi.co/api/people/", {
        method: "GET"
      }).then(res => console.log(res));
    }
  }
};
</script>
