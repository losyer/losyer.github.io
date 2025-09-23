<template>
  <div class="layout">
    <Sidebar
      :is-open="isSidebarOpen"
      @close="closeSidebar"
    />
    <main class="content">
      <button
        type="button"
        class="menu-toggle"
        @click="toggleSidebar"
        :aria-expanded="isSidebarOpen ? 'true' : 'false'"
        aria-controls="site-sidebar"
      >
        <i class="fa fa-bars" aria-hidden="true"></i>
        Menu
      </button>
      <router-view />
    </main>
  </div>
</template>

<script>
import Sidebar from "./components/Sidebar.vue";

export default {
  components: { Sidebar },
  data() {
    return {
      isSidebarOpen: false
    };
  },
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen;
    },
    closeSidebar() {
      this.isSidebarOpen = false;
    }
  }
};
</script>

<style>
.layout {
  display: flex;
}

.content {
  margin-left: 200px; /* サイドバーの幅と同じ */
  padding: 1rem;
  flex: 1;
}

.menu-toggle {
  display: none;
  align-items: center;
  gap: 0.5rem;
  border: none;
  border-radius: 0.5rem;
  padding: 0.6rem 1rem;
  background: #333;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
}

.menu-toggle:focus {
  outline: 2px solid #888;
  outline-offset: 2px;
}

@media (max-width: 768px) {
  .layout {
    flex-direction: column;
  }

  .content {
    margin-left: 0;
    padding: 1.5rem 1rem;
  }

  .menu-toggle {
    display: inline-flex;
    margin-bottom: 1.25rem;
  }
}
</style>
