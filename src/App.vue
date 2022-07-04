<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis" :tooltip="chartTooltip">
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="country" yName="gold"
        name="Gold"></e-series>
        <!-- <e-series type="Column" :dataSource="chartData" xName="country" yName="gold"
        name="Gold" tooltipMappingName='text'></e-series> -->
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries, Category, Tooltip } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [ColumnSeries, Category, Tooltip]},
  data() {
    return {
      chartTooltip : {
        enable : true,
        // template : '<div><table style="width:100%;  border: 1px solid #C1272D;" class="table-borderless"><tr><td style="height: 25px; width: 80px; background-color: #C1272D; font-size: 14px; color: #E7C554; font-weight: bold; padding-left: 5px ">${x}</td></tr><tr><td style="height: 25px; width: 80px; background-color: #C1272D; font-size: 14px; color: #FFFFFF; font-weight: bold; padding-left: 5px">Gold : ${y}</td></tr></table></div>',
        // header : "Medals",
        // format: '${point.tooltip}'
	      // format:"<b>${series.name} : ${point.y}</b>",
        border : {
          color : '#FF0000',
          width : 3
        }
      },
      chartPrimaryYAxis : { title : 'Medals Count'},
      chartTitle : 'Olympic Medals',
      chartPrimaryXAxis : {
        valueType : 'Category',
        title : 'Country'
      },
      chartData : [
          { country : "USA", gold : 50, text: 'Country : USA <br> Gold : 50' },
          { country : "China", gold : 40, text: 'Country : China <br> Gold : 40' },
          { country : "Japan", gold : 70, text: 'Country : Japan <br> Gold : 70' },
          { country : "Australia", gold : 60, text: 'Country : Australia <br> Gold : 60' },
          { country : "France", gold : 50, text: 'Country : France <br> Gold : 50' },
          { country : "Germany", gold : 40, text: 'Country : Germany <br> Gold : 40' },
          { country : "Italy", gold : 40, text: 'Country : Italy <br> Gold : 40' },
          { country : "Sweden", gold : 30, text: 'Country: Sweden <br> Gold : 30' }
      ]
    };
  }
}
</script>





