<template>
    <header>
        <nuxt-link v-if="this.$route.name == 'login'" to="/signin">S'inscrire</nuxt-link>
        <nuxt-link v-else-if="this.$route.name == 'signin' || this.$route.name == 'password'" to="/login">Retour</nuxt-link>
    </header>
</template>

<style lang="scss" scoped>
header{
    font-size: 1rem;
    width: 100%;
    padding: 2.361vw;
    font-family: $Kinetic-Bold;

    p{
        text-align: center;
        width: 100%;
    }
}
</style>