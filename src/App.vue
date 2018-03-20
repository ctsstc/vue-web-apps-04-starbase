<template>
  <div id="app">
    <h2>{{title}}</h2>
    <Character/>
  </div>
</template>

<script>
import Character from "./components/Character";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team"
    };
  },
  components: {
    Character
  }
};
</script>
