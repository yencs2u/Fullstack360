<template>
  <div class="flex h-screen w-full bg-gray-600">
    <div class="m-auto w-full px-5 md:w-1/3">
    <div class="pl-1 text-yellow-400 font-bold font-medium text-2xl tracking-wide text-center">
         Inventory System
    </div>
        <form>
          <div class="my-2">
              <inputElement
                :labelName="'EMAIL'"
                :labelId="'email'"
                :inputType="'email'"
                :model="email"
                @input="email = $event"
                :disabled="false"
              />
           </div>
           <div class="my-2">   
              <inputElement
                :labelName="'PASSWORD'"
                :labelId="'password'"
                :inputType="'password'"
                :model="password"
                @input="password = $event"
                :disabled="false"
              />
            </div>
          <button type="button" class="
              transition
              duration-500
              ease-in-out
              bg-blue-600
              rounded-xs
              w-full
              py-3
              text-white
             font-sans 
              font-bold
              tracking-wide
              hover:bg-blue-700
              hover:text-gray-400
              active:outline-none
              focus:outline-none
          "
          @click="login"
          > SIGN IN </button>
        </form>
      </div>
  </div>
</template>

<script>
    import Logo from '~/components/Logo.vue'
    import InputElement from "~/components/items/Input.vue";
    import ContentCard from '~/components/items/ContentCard.vue';
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

export default {
  components: {
    Logo,
    InputElement
  },
  data: function(){
    return {
      email:"",
      password: ""
    }
},
methods:{
  login: function (){
    this.$router.push("/dashboard")
    }
}
}

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

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
