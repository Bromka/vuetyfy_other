<template>
  <nav>
    <h1 class="subheading grey--text">Projects</h1>
    <v-card max-width="200" height="300" class="grey lighten-3 d-flex flex-column justify-space-between">
        <p class="mx-auto">Calculator</p>
        <v-btn color="success" class="mx-auto mb-3" router :to="'/projects/calc'">Go</v-btn>
    </v-card>
  </nav>
</template>
