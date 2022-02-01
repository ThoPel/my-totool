<template>
  <header>
    <nuxt-link v-if="this.$route.name == 'login'" to="/signin"
      >S'inscrire</nuxt-link
    >
    <nuxt-link
      v-else-if="this.$route.name == 'signin' || this.$route.name == 'password'"
      to="/login"
      >Retour</nuxt-link
    >
    <nuxt-link
      v-else-if="this.$route.name == 'projet' || this.$route.name == 'password'"
      to="/dashboard"
      >Retour au tableau de bord</nuxt-link
    >
    <div v-else></div>

    <nuxt-link
      v-if="this.$route.name == 'projet' || this.$route.name == 'dashboard'"
      to="/login"
      ><img src="~/assets/medias/logout.svg" alt="Se déconnecter"
    /></nuxt-link>
    <div v-else></div>
  </header>
</template>

<style lang="scss" scoped>
header {
  font-size: 1rem;
  width: 100%;
  padding: 2.361vw;
  font-family: $Kinetic-Bold;
  @include flexbox(row, space-between, center);
  position: fixed;
  top: 0;
  left: 0;

  p {
    text-align: center;
    width: 100%;
  }

  img {
    width: 1.5vw;
  }
}
</style>
