<template>
  <aside :class="{ 'is-opened': isOpened }">
    <div class="logo">
      <img
        src="../assets/vue.svg"
        class="logo vue"
        alt="Vue logo"
      />
    </div>
    <div class="menu-toggle-wrap">
      <button
        class="menu-toggle"
        @click="toggleMenu"
      >
        <span class="material-icons"> keyboard_double_arrow_right </span>
      </button>
    </div>
    <div class="menu">
      <h3>Menu</h3>
      <router-link
        class="menu-button"
        to="/"
      >
        <span class="material-icons">home</span>
        <span class="menu-item-text">Home</span>
      </router-link>
      <router-link
        class="menu-button"
        to="/about"
      >
        <span class="material-icons">live_help</span>
        <span class="menu-item-text">About</span>
      </router-link>
      <router-link
        class="menu-button"
        to="/team"
      >
        <span class="material-icons">group</span>
        <span class="menu-item-text">Team</span>
      </router-link>
      <router-link
        class="menu-button"
        to="/contact"
      >
        <span class="material-icons">email</span>
        <span class="menu-item-text">Contanct</span>
      </router-link>
    </div>
    <!-- settings -->
    <div class="flex"></div>
    <div class="menu">
      <router-link
        class="menu-button"
        to="/settings"
      >
        <span class="material-icons">settings</span>
        <span class="menu-item-text">Settings</span>
      </router-link>
    </div>
  </aside>
</template>

<script setup>
import { ref } from "vue";
const isOpened = ref(false);
const toggleMenu = () => {
  isOpened.value = !isOpened.value;
};
</script>

<style lang="scss" scoped>
aside {
  display: flex;
  flex-direction: column;
  width: calc(2rem + 32px);
  overflow: hidden;
  min-height: 100vh;
  padding: 1rem;
  background-color: var(--dark);
  color: var(--light);
  transition: 0.2s ease-out;
  &.is-opened {
    width: var(--sidebar-width);
    .menu-toggle {
      transform: rotate(180deg);
    }
    .menu {
      h3,
      .menu-item-text {
        opacity: 1;
        visibility: visible;
      }
      .menu-item-text {
        margin-left: 1rem;
      }
    }
    .menu-button {
      flex-direction: row;
    }
  }
  @media (max-width: 768px) {
    position: fixed;
    z-index: 99;
    top: 0;
    left: 0;
  }
}
.flex {
  flex: 1 1 0;
}
.menu-toggle-wrap {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 1rem;
  position: relative;
}
.menu-toggle {
  color: var(--light);
  font-size: 2rem;
  width: 2rem;
}
.material-icons {
  &:hover {
    color: var(--primary);
  }
}
.menu {
  h3 {
    padding: 0 1rem 0.5rem;
    font-size: 0.875rem;
    text-transform: uppercase;
  }
  margin: 0 -1rem;
  h3,
  .menu-item-text {
    transition: 0.2s ease-out;
    opacity: 0;
    visibility: hidden;
  }
}
.logo {
  img {
    width: 2rem;
  }
}
.menu-button {
  padding: 0.5rem 1rem;
  color: var(--light);
  display: flex;
  // flex-direction: column;
  align-items: center;
  text-decoration: none;
  .material-icons {
    font-size: 2rem;
  }
  &:hover,
  &.router-link-exact-active {
    color: var(--primary);
    background: rgb(88, 75, 75);
  }
  &.router-link-exact-active {
    border-right: 5px solid var(--primary);
  }
}
</style>
