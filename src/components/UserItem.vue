<template>
  <div>
    <h3>{{ user.name }}</h3>
    <p>{{ user.email }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { User } from '../types/User';

export default defineComponent({
  name: 'UserItem',
  props: {
    user: {
      type: Object as () => User,
      required: true
    }
  }
});
</script>

<style scoped>
/* Add any styles here */
</style>
