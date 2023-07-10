<template>
  <v-container>
    <v-card>
      <v-card-title>Cadastrar Postagem</v-card-title>
      <v-divider></v-divider>
        <v-form class="ma-5" @submit.prevent>
          <v-row>
            <v-col cols="12" sm="6">
              <v-text-field
              v-movel="nome"
              :rules="nomeRegras"
              label="Nome"
              variant="outlined"
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6">
              <v-text-field
              v-movel="email"
              :rules="emailRegras"
              label="E-mail"
              variant="outlined"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-textarea 
                v-model="artigo"
                label="Artigo"
                variant="outlined"
              ></v-textarea>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12" sm="6">
              <v-autocomplete
                label="Categoria"
                :items="categorias"
                item-title="tema"
                item-value="id"
                variant="outlined"
              ></v-autocomplete>
            </v-col>
          </v-row>
          <v-row>
          <v-spacer/>
            <v-btn 
              variant="tonal"
              color="primary"
              class="ma-3"
              >
              Enviar
            </v-btn>
          </v-row>
        </v-form>
      </v-card>
  </v-container>
</template>

<script setup lang="ts">
/**
 * imports
 */
import { ref } from 'vue';

/**
 * Data
 */
  const categorias = ref([
    {tema:'Artigo Científico', id:1},
    {tema:'Celebridades', id:2},
    {tema:'Clima', id:3}, 
    {tema:'Esportes', id:4},
    {tema:'Memes', id:5}, 
    {tema:'Notícias', id:6},  
    {tema:'Política', id:7},
  ])

  /**
   * Methods
   */
 

</script>
