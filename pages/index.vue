<template>
  <div class="analytics-page dark">
    <GmailHeader />
    <div class="analytics-grid">
      <div class="section section1">
        <div class="section-title">Section 1 - Line Chart</div>
        <apexchart type="line" :options="chartOptions1" :series="chartSeries1" :width="getChartWidth()" />
      </div>
      <div class="section section2">
        <div class="section-title">Section 2 - Bar Chart</div>
        <apexchart type="bar" :options="chartOptions2" :series="chartSeries2" :width="getChartWidth()" />
      </div>
      <div class="section section3">
        <div class="section-title">Section 3 - Area Chart</div>
        <apexchart type="area" :options="chartOptions3" :series="chartSeries3" :width="getChartWidth()" />
      </div>
      <div class="section section4">
        <div class="section-title">Section 4 - Pie Chart</div>
        <apexchart type="pie" :options="chartOptions4" :series="chartSeries4" :width="getChartWidth()" />
      </div>
    </div>
  </div>
</template>

<script>
import GmailHeader from '~/components/GmailHeader.vue';
import VueApexCharts from 'vue-apexcharts';

export default {
  components: {
    GmailHeader,
    apexchart: VueApexCharts,
  },
  data() {
    return {
      // Data for charts (customize as needed)
      chartOptions1: {
        chart: {
          id: 'chart1',
        },
        xaxis: {
          categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'],
        },
      },
      chartSeries1: [
        {
          name: 'Category A',
          data: [30, 40, 35, 50, 49, 60, 70],
        },
        {
          name: 'Category B',
          data: [45, 35, 55, 60, 70, 50, 45],
        },
      ],
      chartOptions2: {
        chart: {
          id: 'chart2',
          stacked: true,
        },
        xaxis: {
          categories: ['Category 1', 'Category 2', 'Category 3', 'Category 4', 'Category 5'],
        },
      },
      chartSeries2: [
        {
          name: 'Series 1',
          data: [400, 300, 500, 200, 600],
        },
        {
          name: 'Series 2',
          data: [200, 150, 300, 100, 250],
        },
      ],
      chartOptions3: {
        chart: {
          id: 'chart3',
        },
        xaxis: {
          categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'],
        },
      },
      chartSeries3: [
        {
          name: 'Category X',
          data: [10, 20, 25, 30, 35, 40, 45],
        },
      ],
      chartOptions4: {
        chart: {
          id: 'chart4',
        },
        labels: ['Category Alpha', 'Category Beta', 'Category Gamma', 'Category Delta'],
      },
      chartSeries4: [400, 300, 200, 100],
    };
  },
  methods: {
    getChartWidth() {
      // Calculate the chart width based on the window size
      const windowWidth = window.innerWidth;
      if (windowWidth >= 1024) {
        return '100%'; // For larger screens, set the chart width to 100% of the container
      } else if (windowWidth >= 768) {
        return '500px'; // For tablets and medium-sized screens, set a fixed width of 500px
      } else {
        return '300px'; // For smaller screens (mobile phones), set a fixed width of 300px
      }
    },
  },
};
</script>


<style>
/* Your global styles... */

/* Add your custom styles for the dark mode */
.analytics-page {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.dark {
  background-color: #1a1a1a;
  color: #fff;
}

.analytics-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 20px;
}

.section {
  background-color: #2b2d31;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  padding: 20px;
}

.section-title {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 10px;
}

/* Media query for tablets and small screens */
@media screen and (max-width: 1024px) {
  .analytics-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  }
}

/* Media query for mobile phones */
@media screen and (max-width: 767px) {
  .analytics-grid {
    grid-template-columns: 1fr;
  }
}
</style>