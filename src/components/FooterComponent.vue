<script>
    export default{
        name: "FooterComponent",
        data()
        {
            return{
                social_icons: [
                    // "footer-facebook.png",
                    // "footer-twitter.png",
                    // "footer-youtube.png",
                    "footer-pinterest.png",
                    "footer-periscope.png"
                ]
            }
        },
        methods:
        {
            getImagePath: function(imgPath)
            {
                return new URL(imgPath, import.meta.url).href;
            }
    }
}
</script>

<template>
    <div id="footer_box">
        <img src="../assets/img/dc-logo-bg.png">
        <div id="footer_bottom">
            <div id="sign_up_and_social" class="centered_block">
                <h4>SIGN-UP NOW!</h4>
                <div id="social_flex">
                    <div v-for="(item, index) in social_icons" :key="index">
                        <img :src="getImagePath(`../assets/img/${item}`)">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
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

    #sign_up_and_social
    {
        height: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        h4
        {
            color: white;
            padding: 0.75rem;
            border: 3px solid blue;
            cursor: pointer;
        } 
        #social_flex
        {
            height: 100%;
            border: 1px solid yellow;
            color: blue;
            display: flex;
            align-items: center;
            div
            {
                img
                {
                    width: 30px;
                    height: 30px;
                } 
            } 
        } 
    }
</style>