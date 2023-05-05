<script>
  import NavMenu from "./components/NavMenu.vue"
  import Jumbotron from "./components/Jumbotron.vue"
  import CentralMenu from "./components/CentralMenu.vue"
  import FooterComponent from "./components/FooterComponent.vue"
  import ComicsComponent from "./components/ComicsComponent.vue"
  export default{
    name: "App",
    components: {
      NavMenu,
      Jumbotron,
      CentralMenu,
      FooterComponent,
      ComicsComponent
    }
  }
</script>

<template>
  <div id="page">
    <NavMenu/>
    <main>
      <Jumbotron/>
      <ComicsComponent/>
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

</style>
