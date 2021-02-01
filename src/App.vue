<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>Ejemplo de campo custom, con vuetify</h1>
        <custom-field
        :separators="5"
        v-model="data1"
        ></custom-field>
        <h1>Ejemplo de campo custom, con vuetify, con datos preestablecidos</h1>
        <custom-field
        :separators="4"
        v-model="data2"
        ></custom-field>

        {{$data}}
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

import CustomField from '@/components/CustomField';
export default {
  name: 'App',

  components: {
    CustomField,
  },

  data: () => ({
    data1: undefined,
    data2: ['correr', 'nadar', 'caminar', 'hablar']
  }),
};
</script>
