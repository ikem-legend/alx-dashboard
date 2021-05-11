<template>
  <div class="q-pa-lg full-width">
    <div class="row">
      <div class="col-8">
        <div class="row">
          <q-icon name="waving_hand" class="deep-orange q-mr-sm self-center"></q-icon>
          <span class="text-weight-bold fs-18 deep-orange">Hey User</span>
        </div>
        <div class="row">
          <h6 class="dashboard-name text-weight-bold q-mt-xs q-mb-lg">Your dummy dashboard</h6>
        </div>
        <div class="row">
          <div class="col-md-6 offset-md-3 col-xs-12">
            <chart-payments></chart-payments>
          </div>
        </div>
        <div class="row">
          <div class="col q-pa-sm">
            <chart-payments></chart-payments>
          </div>
          <div class="col q-pa-sm">
            <chart-payments></chart-payments>
          </div>
        </div>
      </div>
      <div class="col-4">
        <stats-messages></stats-messages>
      </div>
    </div>
  </div>
</template>

<script>
  import PaymentHistoryChart from "./charts/PaymentHistory";
  import StatsMessages from "./StatsMessages";

  export default {
    name: "Dashboard",
    components: {
      chartPayments: PaymentHistoryChart,
      statsMessages: StatsMessages
    }
  }
</script>

<style scoped lang="sass">
  .fs-18
    font-size: 1.125em
  .deep-orange
    color: #FFA14E
  .dashboard-name
    color: #1F1F1F
    font-size: 24px
</style>
