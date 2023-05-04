<script>
    export default{
        name: "FooterComponent",
    }
</script>

<template>
    <div id="footer_box">
        <img src="../assets/img/dc-logo-bg.png">
        <div id="footer_bottom">
        </div>
    </div>
</template>

<style lang="scss">
    @use "../style/main.scss" as *;

    #footer_box
    {
        min-height: 45vh;
        background-image: url("../assets/img/footer-bg.jpg");
        padding: 2rem 0;
        position: relative;
        img
        {
            height: calc(100% + $header_height);
            position: absolute;
            bottom: 0;
            left: 50%;
        } 
    }
</style>