<template>
  <v-app>
      <v-app-bar color="grey-darken-3">
      <v-app-bar-nav-icon @click.stop="drawer=!drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>App para testar recursos novos</v-toolbar-title>
      </v-app-bar>
      <v-navigation-drawer
      color="grey-darken-3"
      v-model="drawer"
      >
      <v-list>
        <v-list-item to="/">Home</v-list-item>
        <v-list-item to="/firstpage">Cadastrar Post</v-list-item>
        <v-list-item>Contact</v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main class="gradient-background ">
      <router-view></router-view>
    </v-main>
</v-app>
</template>

<script lang="ts" setup>
/**
 * Imports
 */
import { ref } from 'vue';

/**
 * Data
 */
const drawer = ref(true);



/**
 * Methods 
 */ 

/**
 * Hook
 */

</script>

<style>
.gradient-background {
  background: linear-gradient(to bottom, black, white);
}

</style>