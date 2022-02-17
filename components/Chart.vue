<script>
import { Bar } from 'vue-chartjs'

export default {
  extends: Bar,
  props: ['chartdata'],
  mounted () {
    this.renderChart(this.chartdata, {responsive: true})
  }
}
</script>
