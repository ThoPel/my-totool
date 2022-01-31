<template>
  <div class="switch-color">
    <p
      class="btn btn--light"
      v-if="$colorMode.preference !== 'light'"
      @click="changeTheme('light')"
    >
      LIGHT
    </p>
    <p class="btn btn--dark" v-else @click="changeTheme('dark')">DARK</p>
  </div>
</template>

<script>
export default {
  name: "ColorSwitch",

  methods: {
    changeTheme(theme) {
      this.$colorMode.preference = theme;
    },
  },
};
</script>

<style lang="scss" scoped>
.switch-color {
  cursor: pointer;
  color: $secondary;
  font-size: 2rem;
}
</style>