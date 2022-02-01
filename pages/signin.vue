<template>
  <main>
    <h1>Bienvenue !</h1>
    <form>
      <label for="prenom">Prénom</label>
      <input type="text" name="prenom" />
      <label for="nom">Nom</label>
      <input type="text" name="nom" />
      <label for="e-mail">E-mail</label>
      <input type="e-mail" name="e-mail" />
      <label for="password">Mot de passe</label>
      <input type="password" name="password" />
      <label for="color">Couleur</label>
      <div class="colors" name="color">
          <span style="background: #CF8E2B;"></span>
          <span style="background: #6E1997;"></span>
          <span style="background: #CA32B2;"></span>
          <span class="border" style="background: #D1BF1C;"></span>
          <span style="background: #28C6A9;"></span>
          <span style="background: #4471E3;"></span>
          <span style="background: #A66CF1;"></span>
          <span style="background: #3FAB0C;"></span>
          <span style="background: #C20000;"></span>
          <span style="background: #B5E156;"></span>
      </div>
      <span class="btn">s'inscrire</span>
    </form>
  </main>
</template>

<style lang="scss" scoped>
    .colors{
        @include flexbox(row, space-between, center);
        width: 100%;

        span{
            width: 1.042vw;
            height: 1.042vw;
            border-radius: 5px;

            &.border {
                border: 4px solid $secondary;
            }
        }
    }
</style>
