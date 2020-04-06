<template>
  <div id="employee-table">
    <p v-if="employees.length < 1" class="empty-table">
    No employees
  </p>
    <table v-else>
      <thead>
        <tr>
          <th>Employee ID</th>
          <th>Employee name</th>
          <th>Employee email</th>
          <th>Edit</th>
          <th>Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{employee.id}}</td>
          <td>{{employee.name}}</td>
          <td>{{employee.email}}</td>
          <td><button>Edit</button></td>
          <td>
            <button @click="$emit('delete:employee', employee.id)">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'employee-table',
    props: {
      employees: Array
    }
  }
</script>

<style scoped>

</style>