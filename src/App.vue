<template>
  <v-app>
    <v-app-bar color="pink" height="55" dark absolute>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <v-toolbar-title>Layout - con menu drawer</v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer color="pink" v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="lime lighten-5--text text--accent-4"
        >
          <div class="separador p-0">
            <v-btn absolute right depressed small plain @click="drawer = false">
              <v-icon small>mdi-close</v-icon>
            </v-btn>
          </div>

          <v-list-item>
            <v-list-item-icon>
              <v-icon color="grey lighten-5">mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Inicio</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon color="grey lighten-5">mdi-magnify</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Buscar</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon color="grey lighten-5">mdi-forum</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Acerca de</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-card height="55"> </v-card>
    <v-container class="mt-6">
      <template>
        <v-row>
          <v-col v-for="(personaje, index) in personajes" :key="index" md="4">
            <v-card class="mx-auto" max-width="344">
              <v-img :src="personaje.imagen" height="200px"></v-img>
              <v-card-title>
                {{ personaje.nombre }}
              </v-card-title>
              <v-card-actions>
                <v-btn color="pink" text>
                  Explore
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </template>
    </v-container>
  </v-app>
</template>

<script>
  export default {
    name: "App",

    components: {},

    data: () => ({
      personajes: [
        {
          id: 1,
          nombre: "Morty",
          imagen: "https://rickandmortyapi.com/api/character/avatar/2.jpeg",
        },
        {
          id: 2,
          nombre: "Rick",
          imagen: "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
        },
        {
          id: 3,
          nombre: "Summer",
          imagen: "https://rickandmortyapi.com/api/character/avatar/3.jpeg",
        },
        {
          id: 4,
          nombre: "Beth",
          imagen: "https://rickandmortyapi.com/api/character/avatar/4.jpeg",
        },
        {
          id: 5,
          nombre: "Jerry",
          imagen: "https://rickandmortyapi.com/api/character/avatar/5.jpeg",
        },
      ],
      drawer: false,
      group: null,
    }),
  };
</script>
<style>
  .separador {
    height: 30px;
  }
</style>