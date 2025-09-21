<template>
  <div class="layout">
    <Sidebar />
    <main class="content">
      <router-view />
    </main>
  </div>
</template>

<script>
import Sidebar from "./components/Sidebar.vue";

export default {
  components: { Sidebar }
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
</style>
