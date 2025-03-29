<template>
  <div class="theme-switcher">
    <label>تغییر تم:</label>
    <select v-model="selectedTheme" @change="changeTheme">
      <option value="black-red">مشکی قرمز</option>
      <option value="black-blue">مشکی آبی</option>
      <option value="black-yellow">مشکی زرد</option>
      <option value="black-green">مشکی سبز</option>
      <option value="black-rainbow">مشکی رنگین‌کمان</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "ThemeSwitcher",
  data() {
    return {
      selectedTheme: localStorage.getItem("kuma-theme") || "black-red"
    };
  },
  mounted() {
    this.applyTheme();
  },
  methods: {
    changeTheme() {
      localStorage.setItem("kuma-theme", this.selectedTheme);
      this.applyTheme();
    },
    applyTheme() {
      document.documentElement.setAttribute("data-theme", this.selectedTheme);
    }
  }
};
</script>

<style scoped>
.theme-switcher {
  padding: 10px;
  color: var(--text-color);
}
select {
  background: var(--background);
  color: var(--text-color);
}
</style>
