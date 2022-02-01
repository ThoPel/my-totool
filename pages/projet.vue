<template>
  <main>
    <div>
      <h1>Titre de l’espace de travail</h1>
      <p class="subtitle">
        il te reste <span style="color: #c20000">2 tâches</span>, courage !
      </p>
    </div>
    <div class="wrapper">
      <div class="column"></div>
      <div class="column"></div>
      <div class="column"></div>
      <div class="column"></div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.wrapper {
  max-width: 100vw;
  min-height: 52vh;
  overflow-x: scroll;
  padding-left: 10vw;

  @include flexbox(row, flex-start, flex-start, 2.292vw);

  &:webkit-scrollbar {
    padding-left: 10vw;
  }
}

.column {
  min-width: 25.1vw;
  height: 60px;
  background-color: aqua;

  &:last-child{
      margin-right: 10vw;
  }
}
</style>
