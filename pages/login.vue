<template>
  <main>
    <h1>Bonjour !</h1>
    <form>
      <label for="email">E-mail</label>
      <input type="email" name="email" />
      <label for="password">Mot de passe</label>
      <input type="password" name="password" />
      <nuxt-link to="/dashboard" class="btn">Se connecter</nuxt-link>
      <nuxt-link to="/password">mot de passe oublié</nuxt-link>
    </form>
  </main>
</template>

<style lang="scss" scoped>

</style>
