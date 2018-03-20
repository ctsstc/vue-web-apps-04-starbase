<template>
  <div id="app">
    <h2>{{title}}</h2>
    <div class="col-md-12">
      <Character
        v-for="(id, index) in initial_ids"
        :id="id"
        :key="index"
      />
    </div>
  </div>
</template>

<script>
import Character from "./components/Character";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team",
      initial_ids: [1, 13, 14]
    };
  },
  components: {
    Character
  }
};
</script>
