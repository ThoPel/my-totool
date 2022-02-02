<template>
  <main>
    <div>
      <h1>Titre de l’espace de travail</h1>
      <p class="subtitle">
        il te reste <span style="color: #c20000">2 tâches</span>, courage !
      </p>
      <div class="users">
        <span style="background: #3fab0c">tp</span>
        <span style="background: #d1bf1c">sl</span>
      </div>
    </div>
    <!-- <div class="wrapper"> -->
    <draggable
      v-model="columns"
      group="people"
      @start="drag = true"
      @end="drag = false"
      class="wrapper"
    >
      <div v-for="(column, index) in columns" :key="index" class="column">
        <div class="column_top" :style="'background:' + column.color">
          <input class="title" type="text" :value="column.title" />
          <div>
            <span>1</span>
            <img
              @click="toggleColumnMenu($event)"
              src="~/assets/medias/three-dots.svg"
              alt=""
            />
          </div>
        </div>
        <div class="menu close" :style="'background:' + column.color">
          <p>Changer de couleur</p>
          <p>Supprimer</p>
        </div>
        <div class="column_wrapper">
          <div class="card">
            <div class="card_top">
              <h2>Titre de la tâche</h2>
              <span class="user" style="background: #3fab0c">tp</span>
            </div>
            <p class="card_desc">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam
              pharetra.
            </p>
            <div class="card_checklist">
              <p class="nocheck">Lorem ipsum dolor sit amet.</p>
              <p class="checked">Lorem ipsum dolor sit amet.</p>
              <div class="input">
                <input type="text" placeholder="Ajouter une étape..." />
                <span>1/2</span>
              </div>
            </div>
          </div>
        </div>
        <div class="column_bottom">
          <p>+</p>
          <input type="text" placeholder="Ajouter une tâche" />
        </div>
      </div>

      <div class="column add">
        <div class="top">
          <p>+</p>
          <input type="text" placeholder="Ajouter une colonne" />
        </div>
      </div>
    </draggable>

    <!-- <div class="column">
        <div class="column_top" style="background: #cf8e2b">
          <input class="title" type="text" value="En cours" />
          <div>
            <span>0</span>
            <img
              @click="toggleColumnMenu($event)"
              src="~/assets/medias/three-dots.svg"
              alt=""
            />
          </div>
        </div>
        <div class="menu close" style="background: #cf8e2b">
          <p>Changer de couleur</p>
          <p>Supprimer</p>
        </div>
        <div class="column_wrapper"></div>
        <div class="column_bottom">
          <p>+</p>
          <input type="text" placeholder="Ajouter une tâche" />
        </div>
      </div>

      <div class="column">
        <div class="column_top" style="background: #3fab0c">
          <input class="title" type="text" value="Terminées" />
          <div>
            <span>0</span>
            <img
              @click="toggleColumnMenu($event)"
              src="~/assets/medias/three-dots.svg"
              alt=""
            />
          </div>
        </div>
        <div class="menu close" style="background: #3fab0c">
          <p>Changer de couleur</p>
          <p>Supprimer</p>
        </div>
        <div class="column_wrapper"></div>
        <div class="column_bottom">
          <p>+</p>
          <input type="text" placeholder="Ajouter une tâche" />
        </div>
      </div> -->
    <!-- </div> -->
  </main>
</template>

<script>
import draggable from "vuedraggable";

export default {
  components: {
    draggable,
  },
  data() {
    return {
      columns: [
        { title: "A faire", color: "#C20000" },
        { title: "En cours", color: "#CF8E2B" },
        { title: "Terminées", color: "#3FAB0C" },
      ],
    };
  },
  methods: {
    toggleColumnMenu(event) {
      const classMenu =
        event.target.parentNode.parentNode.nextElementSibling.classList;
      if (classMenu.contains("close")) {
        classMenu.remove("close");
        classMenu.add("open");
      } else {
        classMenu.remove("open");
        classMenu.add("close");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
main {
  @include flexbox(column, flex-start, center, 5vh);
  min-height: calc(100vh - 7.5vw);
}

.wrapper {
  max-width: 100vw;
  min-height: 71vh;
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
  position: relative;

  .menu {
    position: absolute;
    top: 3vw;
    right: 0;
    overflow: hidden;
    height: calc(100% - 3vw);
    z-index: 10;
    border-radius: 0 0 5px 5px;
    @include flexbox(column, flex-start, flex-start);
    transition: width 0.3s ease-in-out;

    &.open {
      width: 100%;
    }

    &.close {
      width: 0;
    }

    p {
      color: $main;
      padding: 1vw;
      cursor: pointer;
      white-space: nowrap;
    }
  }

  &_wrapper {
    overflow-y: scroll;
    max-height: 60vh;
  }

  &:last-child {
    margin-right: 10vw;
  }

  &_top {
    width: 100%;
    height: 3vw;
    border-radius: 5px 5px 0 0;
    padding: 0 1vw;
    @include flexbox(row, space-between, center);
    color: $main;

    > div {
      @include flexbox(row, flex-end, center, 0.5vw);
      span {
        color: $main-50;
        @include font($fs-l, $Kinetic-Bold, null, 1);
        transform: translateY(0.1vw);
      }
      img {
        width: 1.2vw;
        filter: $main-filter;
      }
    }

    .title {
      @include font($fs-l, $Kinetic-Bold, null, 1);
      background: transparent;
      border: 0;
      color: $main;
      width: fit-content;
      width: 80%;
      padding: 0.1vw 0.3vw;
      outline: none;
      cursor: pointer;

      &:focus {
        // outline: solid;
        // outline-width: 2px;
        // outline-color: $main-50;
        border-bottom: 2px solid $main-50;
        transform: translateY(1px);
      }
    }
  }

  &_bottom {
    width: 100%;
    height: 3vw;
    border-radius: 5px 5px 0 0;
    padding: 0 1vw;
    @include flexbox(row, flex-start, center, 0.5vw);
    color: $secondary;

    p {
      @include font($fs-xl, $Kinetic-Regular, null, 1);
    }

    input {
      background: transparent;
      border: none;
      @include font($fs-l, $Kinetic-Regular, null, 1);
      outline: none;

      &::placeholder {
        color: $dark-grey;
      }
    }
  }

  &.add {
    min-height: 3vw;
    background-color: $secondary;
    cursor: pointer;

    .top {
      width: 100%;
      height: 3vw;
      border-radius: 5px 5px 0 0;
      padding: 0 1vw;
      @include flexbox(row, flex-start, center, 0.5vw);
      color: $main;

      p {
        @include font($fs-xl, $Kinetic-Regular, null, 1);
      }

      input {
        background: transparent;
        border: none;
        @include font($fs-l, $Kinetic-Bold, null, 1);
        outline: none;
        color: $main;
        width: 100%;

        &::placeholder {
          color: $dark-grey;
        }
      }
    }
  }
}

.users {
  @include flexbox(row, center, center, 0.5vw);
  width: 100%;
  margin-top: 2vw;

  span {
    padding: 0.5vw;
    border-radius: 100%;
    width: 2vw;
    height: 2vw;
    color: $main;
    text-align: center;
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
      width: 100%;

      span {
        color: $dark-grey;
        @include font($fs-m, Kinetic-Light, null, 1);
        right: 0.2vw;
        bottom: 0;
        position: absolute;
      }

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
