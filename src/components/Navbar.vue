<template>
  <div class="q-pa-sm">

    <div class="row">
      <div class="col-4">
        <q-input v-model="searchText" rounded outlined placeholder="Search">
          <template v-slot:prepend>
            <q-icon name="search" />
          </template>
        </q-input>
      </div>
      <div class="col-1 self-center">
        <q-toggle
          v-model="live"
          color="green-light"
          label="Live"
          class="text-grey-dark"
        />
      </div>
      <div class="col-2">
        <q-btn-dropdown flat class="absolute-center text-grey-dark" label="English">
          <q-list>
            <q-item clickable v-close-popup v-for="language in languages" :key="language">
              <q-item-section>
                <q-item-label>{{ language }}</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </div>
      <div class="col-1 self-center">
        <q-btn flat icon="notifications" class="text-grey-dark"></q-btn>
      </div>
      <div class="col-4">
        <q-btn-dropdown
          flat
          text-color="grey-dark"
          no-caps
          class="full-width"
        >
          <template v-slot:label>
            <div class="row items-center no-wrap">
              <q-avatar>
                <q-img src="../assets/black-avatar.png"></q-img>
              </q-avatar>
              <div class="text-center">
                <span class="text-weight-bold">User Name</span><br>
                <span>Ikem</span>
              </div>
            </div>
          </template>

          <q-list>
            <q-item clickable v-close-popup v-for="menu in userMenu" :key="menu">
              <q-item-section avatar>
                <q-avatar :icon="menu.icon" color="grey-dark" text-color="white" />
              </q-item-section>
              <q-item-section>
                {{ menu.name }}
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    name: "Navbar",
    data() {
      return {
        searchText: '',
        live: true,
        languages: ['English', 'French', 'Swahili', 'Xhosa'],
        userMenu: [
          {
            name: 'Profile',
            icon: 'person'
          },
          {
            name: 'Settings',
            icon: 'settings'
          }
        ]
      }
    }
  }
</script>

<style scoped>

</style>
