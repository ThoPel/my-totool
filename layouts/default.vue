<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
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
  font-family: $Kinetic-Regular;
  height: -webkit-fill-available;
  color: $secondary;
  background-color: $main;
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
  color: inherit;
}

ul,
li {
  list-style: none;
}

main {
  min-height: calc(100vh - 5vw - 7.5vw);
  margin-top: 7.5vw;
  width: 100vw;
  @include flexbox(column, flex-start, center, 15vh);
}

h1 {
  @include font($fs-xxl, $Kinetic-Bold, null, 1);
  width: 100%;
  text-align: center;
}

p.subtitle {
  width: 100%;
  text-align: center;
  @include font($fs-xl, $Kinetic-Bold, null, 1);
}

.add-1 {
  padding: 0.7vw 1vw;
  background-color: $secondary;
  color: $main;
  border-radius: 5px;
  @include font($fs-l, $Kinetic-Regular, null, 1);
  @include flexbox(column, center, center);
  cursor: pointer;
  width: 100%;
  height: 100%;
}

form {
  @include flexbox(column, flex-start, flex-start);
  width: 15vw;

  input {
    width: 100%;
    margin-bottom: 1.389vw;
    border-radius: 5px;
    border: 1px solid $secondary;
    padding: 0.6vw;
    outline: none;
    @include font($fs-l, $Kinetic-Regular, lowercase, 1);
  }

  label {
    width: 100%;
    @include font($fs-l, $Kinetic-Bold, null, 1);
    margin-bottom: 0.347vw;
  }

  .btn {
    width: 100%;
    background-color: $secondary;
    color: $main;
    border-radius: 5px;
    text-align: center;
    padding: 0.6vw;
    margin-bottom: 1.389vw;
    @include font($fs-l, $Kinetic-Bold, lowercase, 1);
    cursor: pointer;
  }

  .colors {
    margin-bottom: 1.389vw;
  }

  a {
    width: 100%;
    text-align: center;
    @include font($fs-m, $Kinetic-Light, lowercase, 1);
  }
}

header,
nav,
section,
main,
article {
  padding: 0 2.361vw;

  @include tablet {
    padding: 0 2.4rem;
  }

  @include mobile {
    padding: 0 1.8rem;
  }
}
</style>
