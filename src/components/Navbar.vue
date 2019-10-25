<template>
  <nav class="">
    <v-navigation-drawer app v-model="drawer" class="blue lighten-4 elevation-4">
      <v-list>
        <v-list-item-group v-model="item" >
          <v-list-item v-for="(item, i) in items" :key="i" router :to="item.route">
            <v-list-item-icon>
              <v-icon v-text="item.icon" class="grey--text text--darken-2"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.text" class="grey--text text--darken-1"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>

        <v-list-item-group  sub-group
          no-action>
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title>Actions</v-list-item-title>
            </v-list-item-content>
          </template>
        </v-list-item-group>
      </v-list>


    </v-navigation-drawer>

    <v-app-bar app class="">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn text color="grey">
        <span>Sign out</span>
        <v-icon>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-app-bar>
  </nav>
</template>


<script>
export default {
  data() {
    return {
      drawer: false,
      item: 0,
      items: [
        { text: "Home", icon: "mdi-clock", route: '/' },
        { text: "About", icon: "mdi-account", route:'/about' },
        { text: "Примеры", icon: "mdi-flag", route:'/projects' }
      ]
    };
  }
};
</script>