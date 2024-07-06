<template>
  <div>
    <h1>User List</h1>
    <UserList :users="users" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import axios from 'axios';
import UserList from './components/UserList.vue'; // Ensure the file extension is correct
import { User } from './types/User';

export default defineComponent({
  name: 'App',
  components: {
    UserList
  },
  data() {
    return {
      users: [] as User[]
    };
  },
  created() {
    this.fetchUsers();
  },
  methods: {
    async fetchUsers() {
      try {
        const response = await axios.get<User[]>('https://jsonplaceholder.typicode.com/users');
        this.users = response.data;
      } catch (error) {
        console.error('Error fetching users:', error);
      }
    }
  }
});
</script>

<style scoped>
/* any styles here */
</style>
