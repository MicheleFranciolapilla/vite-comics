<script>
  import NavMenu from "./components/NavMenu.vue"
  import Jumbotron from "./components/Jumbotron.vue"
  export default{
    name: "App",
    components: {
      NavMenu,
      Jumbotron
    }
  }
</script>

<template>
  <div id="page">
    <header>
      <div class="centered_block">
        <img src="./assets/img/dc-logo.png" alt="logo piccolo">
        <NavMenu/>
      </div>
    </header>
    <main>
      <Jumbotron/>
    </main>
    <footer>
      <div>

      </div>
    </footer>
  </div>
</template>

<style lang="scss">
  @use "./style/main.scss" as *;

  #page{
    background-color: green;
    padding-top: 3vh;
  }

  header{
    div{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      img{
        height: 90%;
      }
    }
  }
</style>
