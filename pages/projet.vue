<template>
  <main>
    <div>
      <h1>Titre de l’espace de travail</h1>
      <p class="subtitle">
        il te reste <span style="color: #c20000">2 tâches</span>, courage !
      </p>
    </div>
    <div class="wrapper">
      <div class="column">
        <div class="column_top" style="background: #c20000">
          <h2>A Faire</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <div class="card">
          <div class="card_top">
            <h2>Titre de la tâche</h2>
            <span class="user" style="background: #3fab0c">tp</span>
          </div>
          <div class="card_progress">
            <div class="card_progress-bar">
              <div style="width: 0%"></div>
            </div>
            <p class="card_progress-value">0/2</p>
          </div>
          <p class="card_desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
            pharetra, vitae eu pellentesque. Enim, tellus arcu cras accumsan vel
            cras tempus.
          </p>
          <div class="card_checklist">
            <p class="nocheck">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <p class="nocheck">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <div class="input">
              <input type="text" placeholder="Ajouter une étape..." />
            </div>
          </div>
        </div>
      </div>

      <div class="column">
        <div class="column_top" style="background: #cf8e2b">
          <h2>En Cours</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <div class="card">
          <div class="card_top">
            <h2>Titre de la tâche</h2>
            <span class="user" style="background: #3fab0c">tp</span>
          </div>
          <div class="card_progress">
            <div class="card_progress-bar">
              <div style="width: 50%"></div>
            </div>
            <p class="card_progress-value">1/2</p>
          </div>
          <p class="card_desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
            pharetra, vitae eu pellentesque. Enim, tellus arcu cras accumsan vel
            cras tempus.
          </p>
          <div class="card_checklist">
            <p class="nocheck">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <p class="checked">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <div class="input">
              <input type="text" placeholder="Ajouter une étape..." />
            </div>
          </div>
        </div>
        <div class="card">
          <div class="card_top">
            <h2>Titre de la tâche</h2>
            <span class="user" style="background: #3fab0c">tp</span>
          </div>
          <div class="card_progress">
            <div class="card_progress-bar">
              <div style="width: 50%"></div>
            </div>
            <p class="card_progress-value">1/2</p>
          </div>
          <p class="card_desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
            pharetra, vitae eu pellentesque. Enim, tellus arcu cras accumsan vel
            cras tempus.
          </p>
          <div class="card_checklist">
            <p class="nocheck">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <p class="checked">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <div class="input">
              <input type="text" placeholder="Ajouter une étape..." />
            </div>
          </div>
        </div>
      </div>
      <div class="column">
        <div class="column_top" style="background: #3fab0c">
          <h2>Terminée</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
      </div>
      <div class="column">
        <div class="column_top" style="background: #a66cf1">
          <h2>Envoyé</h2>
          <img src="~/assets/medias/three-dots.svg" alt="" />
        </div>
        <div class="card">
          <div class="card_top">
            <h2>Titre de la tâche</h2>
            <span class="user" style="background: #3fab0c">tp</span>
          </div>
          <div class="card_progress">
            <div class="card_progress-bar">
              <div style="width: 100%"></div>
            </div>
            <p class="card_progress-value">2/2</p>
          </div>
          <p class="card_desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
            pharetra, vitae eu pellentesque. Enim, tellus arcu cras accumsan vel
            cras tempus.
          </p>
          <div class="card_checklist">
            <p class="checked">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <p class="checked">
              Lorem ipsum dolor sit amet, consectetur adipi elit. Neque cras
              magna metus interdum consectetur varius.
            </p>
            <div class="input">
              <input type="text" placeholder="Ajouter une étape..." />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.wrapper {
  max-width: 100vw;
  min-height: 52.5vh;
  overflow-x: scroll;
  padding-left: 10vw;

  @include flexbox(row, flex-start, flex-start, 2.292vw);

  &:webkit-scrollbar {
    padding-left: 10vw;
  }
}

.column {
  min-width: 25.1vw;
  min-height: 3vw;
  background-color: $grey;
  border-radius: 5px;
  min-height: 270px;

  &:last-child {
    margin-right: 10vw;
  }

  &_top {
    height: 3vw;
    border-radius: 5px 5px 0 0;
    padding: 0 1vw;
    @include flexbox(row, space-between, center);
    color: $main;

    img {
      width: 0.3vw;
    }
  }
}

.card {
  @include flexbox(column, flex-start, flex-start, 0.5vw);
  background-color: $main;
  margin: 1vw;
  padding: 1vw;
  border-radius: 5px;

  &_top {
    @include flexbox(row, space-between, center);
    width: 100%;

    h2 {
      @include font($fs-l, Kinetic-Regular, null, 1);
    }

    span {
      padding: 0.5vw;
      border-radius: 100%;
      width: 2vw;
      height: 2vw;
      color: $main;
      text-align: center;
    }
  }

  &_progress {
    @include flexbox(row, space-between, center);
    width: 100%;
    padding-right: 0.4vw;

    &-bar {
      width: 90%;
      border: 1px solid $secondary;
      border-radius: 10px;
      height: 0.5vw;

      div {
        background-color: $secondary;
        border-radius: 10px;
        height: 100%;
      }
    }
  }

  &_desc {
    @include font($fs-s, $Kinetic-Light, null, 1);
  }

  &_checklist {
    @include flexbox(column, flex-start, flex-start, 0.5vw);
    width: 100%;

    p {
      padding-left: 1.5vw;
      position: relative;
      @include font($fs-m, $Kinetic-Regular, null, 1);

      &.nocheck:before {
        content: "";
        position: absolute;
        width: $fs-m;
        height: $fs-m;
        border: 1px solid $secondary;
        left: 0;
        top: 0;
      }

      &.checked {
        text-decoration: line-through;
        color: $dark-grey;

        &:before {
          content: "✔";
          color: $main;
          @include flexbox(row, center, center);
          font-size: $fs-s;
          position: absolute;
          width: $fs-m;
          height: $fs-m;
          background: $dark-grey;
          left: 0;
          top: 0;
        }
      }
    }
    .input {
      padding-left: 1.5vw;
      position: relative;

      input {
        background: transparent;
        border: none;
        @include font($fs-m, $Kinetic-Regular, null, 1);
        outline: none;

        &::placeholder {
          color: $dark-grey;
        }
      }

      &:before {
        content: "+";
        color: $secondary;
        @include flexbox(row, center, center);
        font-size: $fs-xl;
        position: absolute;
        width: $fs-m;
        height: $fs-m;
        left: 0;
        top: 0;
      }
    }
  }
}
</style>
