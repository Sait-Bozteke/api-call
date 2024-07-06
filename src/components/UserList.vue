<template>
  <div>
    <div v-for="user in users" :key="user.id">
      <UserItem :user="user" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import UserItem from './UserItem.vue'; // Ensure the file extension is correct
import { User } from '../types/User';

export default defineComponent({
  name: 'UserList',
  components: {
    UserItem
  },
  props: {
    users: {
      type: Array as () => User[],
      required: true
    }
  }
});
</script>

<style scoped>
/* Add any styles here */
</style>
