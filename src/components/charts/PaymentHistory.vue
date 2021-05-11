<script>
  import { Bar } from 'vue-chartjs'

  export default {
    extends: Bar,
    data() {
      return {
        chartData: {
          labels: ['Mar 1 - 7', 'Mar 8 - 14', 'Mar 15 - 21', 'Mar 22 - 28', 'Final wk'],
          datasets: [
            {
              label: ['Last 30 days'],
              backgroundColor: '#ECCCFF',
              data: [50000, 125000, 125000, 125000, 175000]
            },
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            y: {
              beginAtZero: true,
              min: 0,
              max: 200000,
              ticks: {
                stepSize: 50000
              }
            }
          }
        }
      }
    },
    mounted() {
      this.renderChart(this.chartData, this.options)
    }
  }
</script>

<style scoped>

</style>
