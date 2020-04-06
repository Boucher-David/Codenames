<template>
  <div id="app">
    <h1>Employees</h1>
    <employee-form @add:employee="addEmployee"/>
    <employee-table :employees="employees" @delete:employee="deleteEmployee"/>
  </div>
</template>

<script>
  import EmployeeTable from '@/components/EmployeeTable.vue'
  import EmployeeForm from '@/components/EmployeeForm'

  export default {
    name: 'app',
    components: {
      EmployeeTable,
      EmployeeForm
    },
    data() {
      return {
        employees: [
        {
          id: 1,
          name: 'Richard Hendricks',
          email: 'richard@piedpiper.com',
        },
        {
          id: 2,
          name: 'Bertram Gilfoyle',
          email: 'gilfoyle@piedpiper.com',
        },
        {
          id: 3,
          name: 'Dinesh Chugtai',
          email: 'dinesh@piedpiper.com',
        },
        {
          id: 4,
          name: 'David Boucher',
          email: 'david@piedpiper.com',
        }
      ]
      }
    },
    methods: {
      addEmployee(employee) {
        employee.id = this.employees.length + 1;
        this.employees = [...this.employees, employee]
      },
      deleteEmployee(employeeId){
        this.employees = this.employees.filter(employee => employee.id !== employeeId);
      }
    }
  }
</script>

<style>
  button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>