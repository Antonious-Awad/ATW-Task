<script>
import { RouterLink } from 'vue-router'
export default {
  name: 'HeaderComponent',
  components: {
    RouterLink
  },

  methods: {
    // A method to define the current active path
    isLinkActive(path) {
      return this.$route.path === path
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <div class="nav-bar">
        <RouterLink to="/" class="logo">Logo</RouterLink>
        <nav>
          <ul>
            <li>
              <RouterLink to="/home" :class="{ active: isLinkActive('/home') }">Home</RouterLink>
            </li>
            <li>
              <RouterLink to="/about" :class="{ active: isLinkActive('/about') }">About</RouterLink>
            </li>
            <li>
              <RouterLink to="/" :class="{ active: isLinkActive('/') }">Project</RouterLink>
            </li>
            <li>
              <RouterLink to="/contact" :class="{ active: isLinkActive('/contact') }"
                >Contact</RouterLink
              >
            </li>
            <li>
              <RouterLink to="/users" :class="{ active: isLinkActive('/users') }">Users</RouterLink>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.nav-bar {
  a {
    text-decoration: none;
    color: #151517;
  }
  .logo {
    font-weight: 700;
    font-size: 22px;
    line-height: 33px;
    text-transform: uppercase;
  }
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100px;
  padding: 0 2rem;
  color: #d8dee9;
  ul {
    list-style: none;
    display: flex;
    gap: 0.5rem;
  }
  nav {
    a {
      font-weight: 500;
      font-size: 16px;
      line-height: 24px;
      margin: 0 1rem;
    }
    .active {
      color: #eebf63;
    }

    a:hover {
      color: #eebf63;
    }
  }
}
</style>
