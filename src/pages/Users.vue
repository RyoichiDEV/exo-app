<template>
  <q-page padding>
    <h6>Utilisateurs:</h6>
    <div class="list row q-gutter-sm">
      <UserCard
        class="col-5"
        :user="utilisateur"
        v-for="utilisateur in users"
        v-bind:key="utilisateur.id"
      >
      </UserCard>
    </div>
  </q-page>
</template>

<script>
import UserCard from 'src/components/UserCard.vue';

export default {
  name: 'User',
  components: {
    UserCard,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    loadAllUsers() {
      this.$axios.get('https://jsonplaceholder.typicode.com/users') // url API
        .then((response) => { // réponse de l'API
          this.users = response.data;
        })
        .catch((error) => {
          console.log('error', error);
        });
    },
  },
  mounted() {
    this.loadAllUsers();
  },
};
</script>
