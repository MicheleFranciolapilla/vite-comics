<script>
    export default{
        name: "Jumbotron",
    }
</script>

<template>
    <div id="jumbo">
    </div>
</template>

<style scoped lang="scss">
@use "../style/main.scss" as *;
    div#jumbo{
        min-height: $jumbotron_height;
        background-image: url("../assets/img/jumbotron.jpg");
    }
</style>