<template>
  <q-layout view="lHh Lpr lFf" class="bg-white">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-2"
    >
      <q-list>
        <q-item-label header class="text-weight-bolder text-32 sidebar-header">Test</q-item-label>
        <q-expansion-item
          v-for="menu in menuItems"
          :key="menu.id"
          :label="menu.parent"
          class="text-weight-bold text-grey-dark"
        >
          <q-separator v-for="menu in menuSeparators" :key="menu.id" />
          <q-item v-for="subMenu in menu.subMenu" :key="subMenu.id" clickable v-ripple>
            <q-item-section avatar>
              <q-icon color="grey-dark" :name="subMenu.icon" />
            </q-item-section>

            <q-item-section class="text-weight-medium text-grey-dark">{{subMenu.name}}</q-item-section>
          </q-item>
          <q-separator />
        </q-expansion-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
  export default {
    name: 'MyLayout',
    data () {
      return {
        leftDrawerOpen: false,
        menuItems: [
          {
            id: 0,
            parent: 'Payments',
            subMenu: [
              {
                id: 11,
                name: 'Transactions',
                icon: 'receipt_long'
              },
              {
                id: 12,
                name: 'Customers',
                icon: 'people'
              },
              {
                id: 13,
                name: 'Payouts',
                icon: 'credit_card'
              },
              {
                id: 14,
                name: 'Balances',
                icon: 'account_balance'
              },
              {
                id: 15,
                name: 'Subscriptions',
                icon: 'check_circle'
              },
              {
                id: 16,
                name: 'Payment plans',
                icon: 'library_books'
              },
            ]
          },
          {
            id: 1,
            parent: 'Commerce',
            subMenu: [
              {
                id: 21,
                name: 'Referrals',
                icon: 'receipt_long'
              },
              {
                id: 22,
                name: 'Audit Logs',
                icon: 'remove_red_eye'
              },
              {
                id: 23,
                name: 'Settings',
                icon: 'settings'
              }
            ]
          }
        ]
      }
    },
    computed: {
      // This method is used to restrict the number of times the menu separator appears
      menuSeparators() {
        return this.menuItems.slice(1)
      }
    }
  }
</script>

<style lang="sass">
  .text-32
    font-size: 2em
  .sidebar-header
    color: #484a4f
</style>
