<template>
  <div class="q-pt-md q-px-sm stats-messages full-height">
    <q-tabs
      v-model="activeTab"
      no-caps
      class="text-grey-dark"
      active-color="grey-dark"
      indicator-color="grey-dark"
    >
      <q-tab name="stats" label="Stats" />
      <q-tab name="messages" label="Messages" :class="activeTab === 'Messages' ? 'text-weight-bold' : ''" />
    </q-tabs>

    <div v-if="activeTab === 'Messages'" class="row q-pa-md">
      <div class="col">
        <q-card class="bg-white message-card q-pa-sm">
          <q-card-section>
            <div>
              <q-icon name="font_download" size="md"></q-icon>
              <span class="float-right">Jan 2, 12:31pm</span>
            </div>
            <div class="q-pt-md">
              <span class="text-weight-bold">James Robinson</span><br />
              <span>I need some maintenance</span>
            </div>
          </q-card-section>
        </q-card>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "StatsMessages",
    data() {
      return {
        activeTab: 'Messages'
      }
    }
  }
</script>

<style scoped lang="sass">
  .stats-messages
    background-color: #F9F9F9
    border-top-left-radius: 0.5em
  .message-card
    border-radius: 0.5em
</style>
