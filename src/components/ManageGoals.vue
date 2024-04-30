<template>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal" />
    <button @click="setGoal">Set Goal</button>

    <!-- teleport makes where th html added to which part of html in dom -->
    <teleport to="">
      <error-alert v-if="inputIsInvalid">
        <h2>Input is Inv alid</h2>
        <p>Please enter few chars...</p>
        <button @click="confirmError">Okay</button>
      </error-alert>
    </teleport>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";

export default {
  components: {
    ErrorAlert,
  },
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    setGoal() {
      const enteredVal = this.$refs.goal.value;
      if (enteredVal === "") {
        this.inputIsInvalid = true;
      }
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>
