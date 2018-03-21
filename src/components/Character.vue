<template>
<div class="col-md-4" @click="switchCharacter">
  <div class="character-card card text-white bg-dark mb-3">
      <div class="card-body">
        <h4 clas="card-title">{{character.name}}</h4>
        <p class="card-text">Height: {{character.height}}</p>
        <p class="card-text">Mass: {{character.mass}}</p>
        <p class="card-text">Hair Color: {{character.hair_color}}</p>
        <p class="card-text">Eye Color: {{character.eye_color}}</p>
      </div>
  </div>
</div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      character: {}
    };
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.co/api/people/${id}/`, {
        method: "GET"
      })
        .then(res => res.json())
        .then(json => (this.character = json));
    },
    switchCharacter() {
      let rndID = Math.floor(Math.random() * 83) + 1;
      this.fetchCharacter(rndID);
    }
  },
  created() {
    this.fetchCharacter(this.id);
  }
};
</script>
