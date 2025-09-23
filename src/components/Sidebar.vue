<!-- src/components/Sidebar.vue -->
<template>
  <aside
    :class="['sidebar', { 'is-open': isOpen }]"
    id="site-sidebar"
  >
    <nav>
      <ul>
        <li>
          <router-link to="/" @click="handleClose">
            <img src="@/assets/icons/home.png" alt="Home Icon" class="icon" />
            Home
          </router-link>
        </li>
        <!-- <li>
          <router-link to="/contact">
            <img src="@/assets/icons/home.png" alt="Contact Icon" class="icon" />
            Contact
          </router-link>
        </li> -->
        <li>
          <router-link to="/contact" @click="handleClose">
            <i class="fa fa-phone fa-fw icon"></i>
            Contact
          </router-link>
        </li> 
        
        <!-- 外部リンク -->
        <li>
          <a href="https://x.com/sasasho8" target="_blank" rel="noopener noreferrer" @click="handleClose">
           <i class="fab fa-twitter-square fa-fw icon"></i>
           Twitter
          </a>
        </li>
        <li>
          <a href="https://www.facebook.com/shota.sasaki.3532" target="_blank" rel="noopener noreferrer" @click="handleClose">
            <i class="fab fa-facebook-square fa-fw icon"></i>
            Facebook
          </a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/shota-sasaki-1b5791165" target="_blank" rel="noopener noreferrer" @click="handleClose">
            <i class="fab fa-linkedin fa-fw icon"></i>
            LinkedIn
          </a>
        </li>
        <li>
          <a href="https://github.com/losyer" target="_blank" rel="noopener noreferrer" @click="handleClose">
            <i class="fab fa-github-square fa-fw icon"></i>
            Github
          </a>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script>
export default {
  props: {
    isOpen: {
      type: Boolean,
      default: false
    }
  },
  emits: ["close"],
  methods: {
    handleClose() {
      this.$emit("close");
    }
  }
};
</script>

<style scoped>
.sidebar {
  width: 200px;
  height: 100vh;
  background: #333;
  color: white;
  position: fixed;
  top: 0;
  left: 0;
  padding-top: 2rem;
}

.sidebar ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.sidebar li {
  margin: 1rem 0;
}

.sidebar a, .sidebar router-link {
  color: white;
  text-decoration: none;
  display: flex;
  align-items: center;
  padding: 0.5rem 1rem;
}

.sidebar a:hover, .sidebar router-link:hover {
  background: #444;
}

.icon {
  width: 20px; /* アイコンサイズ調整 */
  height: 20px;
  margin-right: 0.75rem;
}

@media (max-width: 768px) {
  .sidebar {
    position: static;
    width: 100%;
    height: auto;
    padding: 1rem 1.5rem;
    display: none;
  }

  .sidebar.is-open {
    display: block;
  }

  .sidebar ul {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .sidebar li {
    margin: 0;
  }

  .sidebar a,
  .sidebar router-link {
    padding: 0.5rem 0.75rem;
    border-radius: 0.5rem;
    background: rgba(255, 255, 255, 0.08);
  }

  .sidebar a:hover,
  .sidebar router-link:hover {
    background: rgba(255, 255, 255, 0.18);
  }

  .icon {
    margin-right: 0.35rem;
  }
}
</style>
