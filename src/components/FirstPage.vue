<template>
  <v-container>
    <v-card>
      <v-card-title>Cadastrar Postagem</v-card-title>
      <v-divider></v-divider>
        <v-form class="ma-5">
          <v-row>
            <v-col cols="12" sm="6">
              <v-text-field
              v-model="form.nome"
              label="Nome"
              variant="outlined"
              :rules="[required]"
              required
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6">
              <v-text-field
              v-model="form.email"
              label="E-mail"
              :rules="[required]"
              variant="outlined"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-textarea 
                v-model="form.artigo"
                label="Artigo"
                :rules="[required]"
                variant="outlined"
              ></v-textarea>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12" sm="6">
              <v-autocomplete
                v-model="form.categorias"
                :items="categorias"
                item-title="nome"
                item-value="id"
                :rules="[required]"
                label="Selecione um tema..."
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
              @click="enviar"
              >
              Enviar
            </v-btn>
          </v-row>
        </v-form>
        <v-dialog
          v-model="dialog"
          width="auto"
        >
          <v-card>
            <v-card-title>
              <div class="container">
                Parabéns
              </div>
            </v-card-title>
            <div class="container">
              <v-icon color="success">mdi mdi-check-decagram</v-icon>
            </div>
            <v-card-text>
              Sua postagem foi enviada com sucesso!
            </v-card-text>
            <v-card-actions>
              <v-btn color="error" block @click="dialog = false">Fechar</v-btn>
            </v-card-actions>
          </v-card>
    </v-dialog>
      </v-card>
  </v-container>
</template>

<script setup lang="ts">
/**
 * imports
 */
import { ref } from 'vue';
import { FormularioInterface } from '@/interface/interface';
/**
 * Data
 */
  const dialog = ref(false);
  const categorias = ref([
    {nome:'Artigo Científico', id: 1},
    {nome:'Celebridades', id: 2},
    {nome:'Clima', id: 3},
    {nome:'Esportes', id: 4},
    {nome:'Memes', id: 5},
    {nome:'Notícias', id: 6}, 
    {nome:'Política', id: 7},
  ]);
  const form = ref<FormularioInterface>({
    artigo:"",
    nome:"",
    email:"",
    categorias:"",
});

  /**
   * Methods
   */
 const enviar = () => {
  dialog.value = true;
 }

 const required = (value:string) => {
  return !!value ||'Campo obrigatório';

 }

</script>

<style>
.container {
  display: flex;
  justify-content: center;
  /* outras propriedades de estilo para a div */
}
</style>