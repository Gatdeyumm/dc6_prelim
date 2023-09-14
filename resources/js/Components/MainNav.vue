<script setup>
import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';

const { hidden } = defineProps(['hidden'])
</script>

<template>
  <div class="main-nav">
    <Link :href="route('dashboard')" :active="route().current('dashboard')">
      <i class="fas fa-tachometer-alt"></i> <span :hidden="hidden">Dashboard</span>
    </Link>
    <Link :href="route('clients')" :active="route().current('clients')">
      <i class="fas fa-users"></i> <span :hidden="hidden">Clients</span>
    </Link>
    <Link :href="route('profile.edit')" :active="route().current('profile.edit')">
      <i class="fas fa-user"></i> <span :hidden="hidden">Profile</span>
    </Link>
    <Link :href="route('logout')" method="post">
      <i class="fas fa-sign-out-alt"></i> <span :hidden="hidden">Logout</span>
    </Link>
  </div>
</template>

<style scoped>
/* Your styling goes here */
</style>
