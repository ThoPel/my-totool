<template>
  <Nuxt />
</template>

<style lang="scss">
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: $fs-html;
  height: -webkit-fill-available;
}

body {
  background-color: $main;
  -webkit-font-smoothing: antialiased;
  overflow-x: hidden;
  transition: background-color 0.5s;
  -moz-osx-font-smoothing: grayscale;
}

a {
  text-decoration: none;
  color: $secondary;
}

ul,
li {
  list-style: none;
}

header,
nav,
section,
main,
article {
  padding: 0 6.4rem;

  @include tablet {
    padding: 0 2.4rem;
  }

  @include mobile {
    padding: 0 1.8rem;
  }
}
</style>