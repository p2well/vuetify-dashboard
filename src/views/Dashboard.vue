<template>
  <v-container>
    <h1>Dashboard</h1>

    <v-row>
      <v-col v-for="sale in sales" :key="`${sale.title}`">
        <SalesGraph :sale="sale" />
      </v-col>
    </v-row>

    <v-row>
      <v-col v-for="statistic in statistics" :key="`${statistic.title}`">
        <StatisticCard :statistic="statistic" />
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="8">
        <EmployeesTable :employees="employees" @select-employee="setEmployee" />
      </v-col>
      <v-col cols="4">
        <EventTimeline :timeline="timeline" />
      </v-col>
    </v-row>

    <v-snackbar v-model="snackbar">
      You have selected {{ selectedEmployee.name }},
      {{ selectedEmployee.title }}
      <v-btn color="pink" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>
  </v-container>
</template>

<script>
import EmployeesTable from '@/components/EmployeesTable.vue';
import SalesGraph from '@/components/SalesGraph.vue';
import StatisticCard from '@/components/StatisticCard.vue';
import EventTimeline from '@/components/EventTimeline.vue';

import employeesData from '@/data/employees.json';
import salesData from '@/data/sales.json';
import statisticsData from '@/data/statistics.json';
import timelineData from '@/data/timeline.json';

export default {
  name: 'DashboadPage',
  components: {
    EmployeesTable,
    SalesGraph,
    StatisticCard,
    EventTimeline
  },
  data() {
    return {
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false,
      employees: employeesData,
      sales: salesData,
      statistics: statisticsData,
      timeline: timelineData
    };
  },
  methods: {
    setEmployee(event) {
      this.snackbar = true;
      this.selectedEmployee.name = event.name;
      this.selectedEmployee.title = event.title;
    }
  }
};
</script>

<style scoped></style>
