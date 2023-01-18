<template>
  <div>
    <section class="section">
        <img class="is-flex-mobile img-rick" src="https://i.pinimg.com/originals/ca/f8/a9/caf8a9529d20f213eccdc6f3c611964f.png" alt="RickandMortyLogo">
        <h1 class="title-rick">Personajes de Rick and Morty</h1>
    </section>
    <personajes></personajes>
  </div>
</template>

<script>
import Personajes from './components/Personajes.vue';
  export default {
    components: {
      Personajes
    }
  }

</script>