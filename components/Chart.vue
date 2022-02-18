<template>
    <canvas ref="canvas"  height="120"></canvas>
</template>
<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  props: {color:String, data:Array, border: String},
  data() {
    return {
      gradient: null,
      gradient2: null,
      options: {
        legend: {
          display: false
        },

        scales: {
        yAxes: [{
        ticks: {
          beginAtZero: true,
          display: false
        },
        gridLines: {
          display: false,
        },
      }],
      xAxes: [{
        gridLines: {
          display: false,
        },
      }]
    }
      }

    };
  },
  mounted() {
    console.log('mounted chart');
    this.gradient = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);


    this.renderChart(
      {
        labels: ["","","","",""],
        datasets: [
          {
            label: "",
            borderColor: this.border,
            pointBackgroundColor: "white",
            borderWidth: 1,
            pointBorderColor: "white",
            backgroundColor: this.color,
            data: this.data
          },
        ],

      },
      this.options
    );
  }
};
</script>
