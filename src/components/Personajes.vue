<template>
  <section>
    <div class="columns is-multiline is-desktop">
    <div class="column is-4" v-for="(personaje, p) in personajes " :key="p">
      <div class="card mx-5" v-on:click="alerta" :data-name="personaje.name">
        <div class="card-image">
          <figure class="image is-4">
            <img :src="personaje.image">
          </figure>
        </div>
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <figure class="image is-48x48">
                  <img src="https://i.pinimg.com/originals/ca/f8/a9/caf8a9529d20f213eccdc6f3c611964f.png">
              </figure>
            </div>
            <div class="media-content">
              <p class="title is-4">{{ personaje.name }}</p>
              <p class="subtitle is-6">{{ personaje.status }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  </section>
</template>

<script>
import axios from "axios";
export default{
  beforeMount: function() {
    let url="https://rickandmortyapi.com/api/character"
    let currentObj = this;
    axios(url).then(function(response){
      console.log(response.data.results);
      currentObj.personajes = response.data.results;
    })
  },
  data: function(){
    return {
      busqueda: '',
      personajes: []
    }
  },
  methods: {
    alerta: function(evt){
      alert(evt.currentTarget.dataset["name"])
    },
  }
}

</script>