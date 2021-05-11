<template>
  <q-page class="flex row">
    <app-dashboard></app-dashboard>
  </q-page>
</template>

<script>
import Dashboard from "../components/Dashboard";

export default {
  name: 'PageIndex',
  components: {
    appDashboard: Dashboard
  }
}
</script>
