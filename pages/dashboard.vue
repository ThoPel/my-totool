<template>
  <main>
    <div>
      <h1>Au travail <span style="color: #3fab0c">Thomas</span> !</h1>
      <p class="subtitle">
        Tu as 4 projets en cours, tu as de quoi t’occuper !
      </p>
    </div>
    <div class="wrapper">
      <span class="add-1">+ Nouveau projet</span>

      <nuxt-link to="projet" class="card">
        <div class="card_top">
          <h2>Titre de l'espace de travail</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <p class="card_infos">Ce projet contient 4 tâches</p>
        <p class="card_infos">Dernière modification le : 10/11/2021 à 11h36</p>
        <div class="card_users">
          <span style="background: #3fab0c">tp</span>
          <span style="background: #d1bf1c">sl</span>
        </div>
      </nuxt-link>

      <nuxt-link to="projet" class="card">
        <div class="card_top">
          <h2>Titre de l'espace de travail</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <p class="card_infos">Ce projet contient 4 tâches</p>
        <p class="card_infos">Dernière modification le : 10/11/2021 à 11h36</p>
        <div class="card_users">
          <span style="background: #3fab0c">tp</span>
          <span style="background: #d1bf1c">sl</span>
        </div>
      </nuxt-link>

      <nuxt-link to="projet" class="card">
        <div class="card_top">
          <h2>Titre de l'espace de travail</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <p class="card_infos">Ce projet contient 4 tâches</p>
        <p class="card_infos">Dernière modification le : 10/11/2021 à 11h36</p>
        <div class="card_users">
          <span style="background: #3fab0c">tp</span>
          <span style="background: #d1bf1c">sl</span>
        </div>
      </nuxt-link>

      <nuxt-link to="projet" class="card">
        <div class="card_top">
          <h2>Titre de l'espace de travail</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <p class="card_infos">Ce projet contient 4 tâches</p>
        <p class="card_infos">Dernière modification le : 10/11/2021 à 11h36</p>
        <div class="card_users">
          <span style="background: #3fab0c">tp</span>
          <span style="background: #d1bf1c">sl</span>
        </div>
      </nuxt-link>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.wrapper {
  width: 80vw;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 2.292vw;
}

.card {
  @include flexbox(column, flex-start, flex-start, 0.3vw);
  background-color: $main;
  border: 2px solid $dark-grey;
background-color: $grey;
  border-radius: 5px;
  padding: 0.6vw;

  &_top {
    @include flexbox(row, space-between, center);
    width: 100%;

    img {
      width: 1.2vw;
      filter: $secondary-filter;
    }
  }

  &_infos {
    @include font($fs-m, $Kinetic-Light, null, 1);
  }

  &_users {
    @include flexbox(row, flex-start, center, 0.5vw);

    span {
      padding: 0.5vw;
      border-radius: 100%;
      width: 2vw;
      height: 2vw;
      color: $main;
      text-align: center;
    }
  }
}
</style>
