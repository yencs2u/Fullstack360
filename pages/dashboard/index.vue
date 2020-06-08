<template>
    <div class="flex flex-col">
    </div>
</template>
<script>
    import ContentCard from "~/components/items/ContentCard.vue";
    import BarChart from '~/components/charts/BarChart';
    import LineChart from '~/components/charts/LineChart';

    const chartColors = {
      red: 'rgb(225, 99, 132)',
      orange: 'rgb(255, 159, 64)',
      yellow: 'rgb(255, 205, 86)',
      green: 'rgb(75, 192, 192)',
      blue: 'rgb(54, 162, 235)',
      purple: 'rgb(153, 102, 255)',
      grey: 'rgb(201, 203, 207)',
    };

export default{
    layout: "dashboard",
    components:{
        ContentCard,
        BarChart,
        LineChart
    },
   data(){
      return {
        revenueMonthly: {
          barChartData: {
            labels: ['Jan','Feb','Mar','Apr','May'],
            datasets: [
              {
                label: 'Income',
                backgroundColor: [
                  chartColors.green,
                  chartColors.green,
                  chartColors.green,
                  chartColors.green,
                  chartColors.green],
                data: [5, 3, 4, 6, 4]
              }
           ],
          },
           barChartOptions: {
             responsive: true,
             legend: {
               desplay: false,
             },
             title: {
               display: true,
               text: 'Monthly Income'
             },
             scales: {
               yAxes: [
                 {
                   ticks: {
                     beginAtZero: true,
                     suggestedMax: 10
                   }
                 }
              ]
             }
           },
            }
        }
      },
}
</script>