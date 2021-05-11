<template>
  <div class="q-pa-sm stats-messages">
    <q-tabs
      v-model="tab"
      no-caps
      class="text-grey-dark shadow-2"
    >
      <q-tab name="stats" label="Stats" />
      <q-tab name="messages" label="Messages" />
    </q-tabs>
  </div>
</template>

<script>
  export default {
    name: "StatsMessages"
  }
</script>

<style scoped lang="sass">
  .stats-messages
    background-color: #F9F9F9
  border-top-left-radius: 0.5em
</style>
