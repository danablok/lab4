<template>
<div>
  <h2>Зоряні війни/ Star Wars</h2>
  <div class="col" v-for="film in films" :key="film.episode_id">	
		<router-link :to="{ name:'film', params:{id:film.id} }">{{ film.title }}</router-link>
  </div>
</div>
</template>

<script>
import axios from 'axios';
export default {
  data: () => ({
    films:[]
  }), 
  
  async created() {
    const {data} = await axios.get("https://swapi.co/api/films/");
    this.films = data.results.map(film => {
      let parse_url = film.url.split('/');
      film.id = parse_url[parse_url.length - 2];
      
      return film;
    });
  }
  
}
</script>

<style lang="scss">
.col {
  margin-bottom: 20px;
  font-size: 18px;
}

h2 {  
  font-family: 'Times New Roman', Times, serif;
  font-weight: bold;
  font-size: 36px;
  color: white;
}


</style>

