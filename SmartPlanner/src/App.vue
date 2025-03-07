<template>
  <div id="app">
    <SideNavbar @page-changed="handlePageChange" />
    <div class="content">
      <!-- Placeholder for your content -->
      <div v-if="currentPage === 'dashboard'" class="page-content">
        Dashboard Content will go here
      </div>
      <div v-else-if="currentPage === 'calendar'" class="page-content">
        Calendar Content will go here
      </div>
      <div v-else-if="currentPage === 'tasks'" class="page-content">
        Tasks & Events Content will go here
      </div>
      <div v-else-if="currentPage === 'invites'" class="page-content">
        Invites Content will go here
      </div>
      <div v-else-if="currentPage === 'settings'" class="page-content">
        Settings Content will go here
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import SideNavbar from './components/SideNavbar.vue';

const currentPage = ref('dashboard');

function handlePageChange(page) {
  currentPage.value = page;
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Arial', sans-serif;
}

body {
  background-color: #f5f5f5;
}

#app {
  display: flex;
}

.content {
  flex: 1;
  margin-left: 220px; /* Width of the sidebar */
  padding: 20px;
}

.page-content {
  background-color: white;
  border-radius: 10px;
  padding: 20px;
  min-height: 100vh;
}
</style>