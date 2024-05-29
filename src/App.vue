<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<script>
export default {
  mounted() {
    const initUserTheme = this.getTheme() || this.getMediaPreference();
    this.setTheme(initUserTheme);
  },

  data() {
    return {
      userTheme: "lightMode",
    };
  },

  methods: {
    toggleTheme() {
      const activeTheme = localStorage.getItem("user-theme");
      if (activeTheme === "lightMode") {
        this.setTheme("darkMode");
      } else {
        this.setTheme("lightMode");
      }
    },

    getTheme() {
      return localStorage.getItem("user-theme");
    },

    setTheme(theme) {
      localStorage.setItem("user-theme", theme);
      this.userTheme = theme;
      document.documentElement.className = theme;
    },

    getMediaPreference() {
      const hasDarkPreference = window.matchMedia(
        "(prefers-color-scheme: dark)"
      ).matches;
      if (hasDarkPreference) {
        return "darkMode";
      } else {
        return "lightMode";
      }
    },
  },
};
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/stream">Stream</RouterLink>
        <RouterLink to="/youtube">YouTube</RouterLink>
        <RouterLink to="/links">Liens</RouterLink>

        <div class="card">
          <input
            @change="toggleTheme"
            id="checkbox"
            type="checkbox"
            class="switch-checkbox"
          />
          <label for="checkbox" class="switch-label">
            <span>🌙</span>
            <span>☀️</span>
            <div
              class="switch-toggle"
              :class="{ 'switch-toggle-checked': userTheme === 'darkMode' }"
            ></div>
          </label>
        </div>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
</style>
