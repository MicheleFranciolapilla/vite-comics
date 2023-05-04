<script>
  import NavMenu from "./components/NavMenu.vue"
  import Jumbotron from "./components/Jumbotron.vue"
  import CentralMenu from "./components/CentralMenu.vue"
  import FooterComponent from "./components/FooterComponent.vue"
  export default{
    name: "App",
    components: {
      NavMenu,
      Jumbotron,
      CentralMenu,
      FooterComponent
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
      <CentralMenu/>
    </main>
    <footer>
      <FooterComponent/>
    </footer>
  </div>
</template>

<style lang="scss">
  @use "./style/main.scss" as *;

  #page
  {
    background-color: rgb(23, 23, 23);
    padding: 3vh 0;
  }

  header
  {
    div
    {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;
      img
      {
        height: 90%;
      }
    }
  }
</style>
