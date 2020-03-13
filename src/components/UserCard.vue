<template>
  <div>
    <q-card bordered class="my-card">
      <q-card-section>
        <div class="text-h6">{{user.name}}</div>
        <div class="text-subtitle2">#{{user.id}} | {{user.company.name}}</div>
        <div class="text-subtitle3">{{user.company.catchPhrase}}</div>
      </q-card-section>

      <q-separator inset />

      <q-card-section>
        <ul>
          <li>Email: {{user.email}}</li>
          <li>Phone: {{user.phone}}</li>
          <li>Address: {{user.address.street}}</li>
        </ul>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  name: 'UserCard',
  props: {
    user: {
      type: Object,
    },
  },
};
</script>
<style lang="stylus" scoped>
  .username {
    font-size: large
  }
</style>
