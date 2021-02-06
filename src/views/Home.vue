<template>
  <div class="home">
    <ApolloQuery :query="require('@/graphql/queries/Breeds.gql') ">

    <template slot-scope="{ result: { data},isLoading }">
  
      <div v-if="isLoading">Loading...</div>
      <div class="container" v-else>
        <div class="row breedcol" v-for="breed of data.breeds" :key="breed.id">
        
          <div class="column">
            <div class="card grid">
             
              <p><strong>Cat Breed:</strong> {{ breed.name }} </p> 
              <p><strong> Origin: </strong> {{ breed.origin }} </p>
              <p><strong> Temperament: </strong>{{ breed.temperament }} </p>
              <p><strong>Adaptability Rating: </strong>{{ breed.adaptability }} </p>
              <p><strong> Intelligence Rating:</strong>{{ breed.intelligence }} </p>
              <p><strong>Child_friendly Rating:</strong>{{ breed.child_friendly }} </p>
        
            </div>
          </div>
        </div>
      </div>
    </template>
  </ApolloQuery>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  
  },
}
</script>
<style>
.column {
  float: left;
  width: 25%;
  padding: 15px 15px;
}
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
    display: block;
    margin-bottom: 20px;
  }
}
strong{
color: #09265c;
}
.card {
  background-color: #ebdff0;
  text-align: left;
   border: 5px solid #09265c;
    border-top-left-radius: 4.25rem;
    border-bottom-right-radius: 4.25rem;
    padding: 12px 12px;
    background: linear-gradient(229.28deg, rgba(5, 19, 45, 0.39) 12.44%, rgba(134, 38, 150, 0.14) 29.04%, rgba(146, 128, 46, 0.37) 52.64%, rgba(5, 19, 45, 0.35) 74.56%);

}
</style>