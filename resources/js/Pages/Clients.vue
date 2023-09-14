<script setup>
import Layout from '@/Layouts/Layout.vue';
import { Head } from '@inertiajs/vue3';
</script>


<template>
    <Layout>
      <div class="p-8 text-gray-900">
    <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 md:grid-cols-3">
        <div v-for="client in clients.data" :key="client.id">
            <div class="w-full h-full p-6 text-white bg-blue-500 rounded-lg shadow-lg"> <!-- Fixed height and width -->
                <div class="flex flex-col items-center h-full">
                    <div class="text-5xl">
                        <i class="fas fa-user"></i>
                    </div>
                    <div class="mt-4 text-3xl font-bold text-center">
                        {{ client.first_name }} {{ client.last_name }}
                    </div>
                    <div class="mt-4 text-xl text-center text-gray-200">
                        {{ client.address }}
                    </div>
                    <div class="mt-4 text-xl text-center text-gray-200">
                        {{ client.phone }}
                    </div>
                    <div class="mt-4 text-xl text-center text-gray-200">
                        {{ client.level }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

  
      <div class="flex items-center justify-center mt-4">
        <div class="flex items-center space-x-4">
          <span v-if="clients.prev_page_url">
            <a
              :href="clients.prev_page_url"
              @click.prevent="$inertia.visit(clients.prev_page_url)"
              class="flex items-center px-4 py-2 text-sm font-medium text-white bg-blue-500 rounded-md hover:bg-blue-600"
            >
              <i class="mr-2 fas fa-chevron-left"></i> Page {{ clients.current_page - 1 }}
            </a>
          </span>
  
          <span v-if="clients.next_page_url">
            <a
              :href="clients.next_page_url"
              @click.prevent="$inertia.visit(clients.next_page_url)"
              class="flex items-center px-4 py-2 text-sm font-medium text-white bg-blue-500 rounded-md hover:bg-blue-600"
            >
              Page {{ clients.current_page + 1 }} <i class="ml-2 fas fa-chevron-right"></i>
            </a>
          </span>
        </div>
      </div>
    </Layout>
  </template>

<script>
export default {
    props: {
        clients: Object, // Define the clients prop type as an object
    },
};
</script>
