<template>
  <nav>
    <h1 class="subheading grey--text">It`s Homepage</h1>
    <v-container fluid grid-list-xs class="grey--text text--darken-2">
      <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ad laborum, soluta enim officiis explicabo nam exercitationem repudiandae distinctio cumque veritatis ipsa quae non laboriosam ducimus placeat tempore minima. Numquam, dolore.</p>
    </v-container>
    <v-container fluid class="grey lighten-5">
      <v-row >
        <v-col v-for="n in 3" :key="n" cols="12" sm="4">
          <v-card class="pa-2" outlined tile>One of three columns</v-card>
        </v-col>
      </v-row>
      
    </v-container>
  </nav>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  data() {
    return {};
  }
};
</script>
