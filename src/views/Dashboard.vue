<template>
  <div>
    <h1>Dashboard</h1>

    <SalesGraph v-for="sale in sales" :key="`${sale.title}`" :sale="sale" />

    <EmployeesTable :employees="employees" @select-employee="setEmployee" />

    <v-snackbar v-model="snackbar">
      You have selected {{ selectedEmployee.name }},
      {{ selectedEmployee.title }}
      <v-btn color="pink" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>
  </div>
</template>

<script>
import EmployeesTable from '@/components/EmployeesTable.vue';
import SalesGraph from '@/components/SalesGraph.vue';

import employeesData from '@/data/employees.json';
import salesData from '@/data/sales.json';

export default {
  name: 'DashboadPage',
  components: {
    EmployeesTable,
    SalesGraph
  },
  data() {
    return {
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false,
      employees: employeesData,
      sales: salesData
    };
  },
  methods: {
    selectRow(event) {
      this.snackbar = true;
      this.selectedEmployee.name = event.name;
      this.selectedEmployee.title = event.title;
    }
  }
};
</script>

<style scoped></style>
