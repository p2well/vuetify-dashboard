<template>
  <div>
    <h1>Dashboard</h1>

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

import employeesData from '../data/employees.json';

export default {
  name: 'DashboadPage',
  components: {
    EmployeesTable
  },
  data() {
    return {
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false,
      employees: employeesData
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
