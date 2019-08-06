<template>
  <div class="content">
    <div class="md-layout">
    <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-100 md-size-100"
      >
        <md-card>
          <md-card-header data-background-color="green">
            <h4 class="title">MARKET INSIGHT</h4>
           
          </md-card-header>
          <stats-card data-background-color="green">
          <template slot="header">
            <md-icon>store</md-icon>
          </template>

          <template slot="content">
            <p class="category">Sales Turnover</p>
            <h3 class="title">Rp.3.600.000</h3>
          </template>

          <template slot="footer">
             <p class="category">
              <span class="text-success"
                ><i class="fas fa-long-arrow-alt-down"></i> 12.8%
              </span>
              Last Period Product Sold
            </p>
            
          </template>
        </stats-card>
    
        </md-card>
      </div>
    <transition name="fade">
            <router-view> </router-view>
        </transition>
        <template>
  <div>
    <date-picker v-model="time1" valueType="format" :first-day-of-week="1"></date-picker>
    <date-picker v-model="time2" type="datetime" :time-picker-options="timePickerOptions"></date-picker>
    <date-picker v-model="time3" range :shortcuts="shortcuts"></date-picker>
    <date-picker v-model="value" :lang="lang"></date-picker>
  </div>
</template>
     
      <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-100 md-size-33"
      >
      
        <chart-card
          :chart-data="emailsSubscriptionChart.data"
          :chart-options="emailsSubscriptionChart.options"
          :chart-responsive-options="emailsSubscriptionChart.responsiveOptions"
          :chart-type="'Bar'"
          data-background-color="red"
        >
          <template slot="content">
            <h4 class="title">AVERAGE PURCHASE VALUE</h4>
           
          </template>

          <template slot="footer">
            <div class="stats">
              <md-icon>access_time</md-icon>
              updated 1 days ago
            </div>
          </template>
        </chart-card>
      </div>
    
       <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-75 md-size-35"
      >
        <md-card>
          <md-card-header data-background-color="orange">
            <h4 class="title">BEST SELLING SKU</h4>
            
          </md-card-header>
          
          <md-card-content>
            <ordered-table table-header-color="orange"></ordered-table>
          </md-card-content>
          
            <div class="stats">
              <md-icon>access_time</md-icon>
              updated 1 days ago
            </div>
        
        </md-card>
      </div>
        <div
        class="md-layout-item md-medium-size-100 md-xsmall-size-75 md-size-30"
      >
        <md-card>
          <md-card-header data-background-color="green">
            <h4 class="title">TOP COMPETITOR SKU</h4>
            
          </md-card-header>
          <md-card-content>
            <simple-table table-header-color="green"></simple-table>
          </md-card-content>
          <div class="stats">
              <md-icon>access_time</md-icon>
              updated 1 days ago
            </div>
        </md-card>
      </div>
          
     
    </div>
  </div>
</template>


<script>
import {
  StatsCard,
  ChartCard,
  NavTabsCard,
  NavTabsTable,
  SimpleTable,
  OrderedTable
} from "@/components";

export default {
  components: {
    StatsCard,
    ChartCard,
    NavTabsCard,
    NavTabsTable,
     SimpleTable,
    OrderedTable
  },
  data() {
    return {
      dailySalesChart: {
        data: {
          labels: ["M", "T", "W", "T", "F", "S", "S"],
          series: [[12, 17, 7, 17, 23, 18, 38]]
        },
        options: {
          lineSmooth: this.$Chartist.Interpolation.cardinal({
            tension: 0
          }),
          low: 0,
          high: 50, // creative tim: we recommend you to set the high sa the biggest value + something for a better look
          chartPadding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0
          }
        }
      },
      dataCompletedTasksChart: {
        data: {
          labels: ["12am", "3pm", "6pm", "9pm", "12pm", "3am", "6am", "9am"],
          series: [[230, 750, 450, 300, 280, 240, 200, 190]]
        },

        options: {
          lineSmooth: this.$Chartist.Interpolation.cardinal({
            tension: 0
          }),
          low: 0,
          high: 1000, // creative tim: we recommend you to set the high sa the biggest value + something for a better look
          chartPadding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0
          }
        }
      },
      emailsSubscriptionChart: {
        data: {
          labels: [
            "Ja",
            "Fe",
            "Ma",
            "Ap",
            "Mai",
            "Ju",
            "Jul",
            "Au",
            "Se",
            "Oc",
            "No",
            "De"
          ],
          series: [[542, 443, 320, 780, 553, 453, 326, 434, 568, 610, 756, 895]]
        },
        options: {
          axisX: {
            showGrid: false
          },
          low: 0,
          high: 1000,
          chartPadding: {
            top: 0,
            right: 5,
            bottom: 0,
            left: 0
          }
        },
        responsiveOptions: [
          [
            "screen and (max-width: 640px)",
            {
              seriesBarDistance: 5,
              axisX: {
                labelInterpolationFnc: function(value) {
                  return value[0];
                }
              }
            }
          ]
        ]
      }
    };
  }
};
</script>
