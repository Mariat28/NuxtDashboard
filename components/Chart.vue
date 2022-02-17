<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  data() {
    return {
      gradient: null,
      gradient2: null,
      options:{
        legend: {
          display : false,
        }
      }
    };
  },
  mounted() {
    this.gradient = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);

    this.gradient.addColorStop(0, "rgba(255, 0,0, 0.5)");
    this.gradient.addColorStop(0.5, "rgba(255, 0, 0, 0.25)");
    this.gradient.addColorStop(1, "rgba(255, 0, 0, 0)");

    this.renderChart(
      {
        labels: [
          "",
          "",
          "",
          "",
          "",
          "",


        ],
        datasets: [
          {
            label: "",
            borderColor: "white",
            pointBackgroundColor: "white",
            borderWidth: 0,
            pointBorderColor: "white",
            backgroundColor: this.gradient,
            data: [0, 10, 40, 38, 80, 0]
          },
        ],
      },
      { responsive: true, maintainAspectRatio: false }
    );
  }
};
</script>