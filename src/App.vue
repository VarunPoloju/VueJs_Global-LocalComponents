<template>
  <div>
    <the-header></the-header>
    <!-- <TheHeader/> -->
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>

    <!-- dynamic component below -->
    <keep-alive>
      <component :is="selectedComponent"> </component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
import ManageGoals from "./components/ManageGoals.vue";

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedComponent: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },

  methods: {
    setSelectedComponent(comp) {
      this.selectedComponent = comp;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
