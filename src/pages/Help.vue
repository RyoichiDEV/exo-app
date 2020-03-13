<template>
  <q-page padding class="bg-white">
    <h6>Help page</h6>
    <div class="row q-mb-md">
      <q-input v-model="nom" label="Nom" class="col-4"></q-input>
    </div>
    <q-btn @click="envoyerNom" color="primary" icon="send" label="Envoyer"></q-btn>
  </q-page>
</template>

<script>
export default {
  name: 'Help',
  data() {
    return {
      nom: '',
    };
  },
  methods: {
    envoyerNom() {
      this.$q.dialog({
        title: 'Envoi nom',
        message: `Votre nom est ${this.nom}`,
      });
    },
  },
};
</script>
