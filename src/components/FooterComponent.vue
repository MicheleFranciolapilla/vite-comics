<script>
    export default{
        name: "FooterComponent",
        data()
        {
            return{
                footer_menus: [
                                {
                                    list_title  : "DC COMICS",
                                    list        : [
                                                    "Characters",
                                                    "Comics",
                                                    "Movies",
                                                    "TV",
                                                    "Games",
                                                    "Videos",
                                                    "News"
                                                ]
                                },
                                {
                                    list_title  : "SHOP",
                                    list        : [
                                                    "Shop DC",
                                                    "Shop DC Collectibles"
                                                ]
                                },
                                {
                                    list_title  : "DC",
                                    list        : [
                                                    "Terms Of Use",
                                                    "Privacy policy (New)",
                                                    "Ad Choices",
                                                    "Advertising",
                                                    "Jobs",
                                                    "Subscriptions",
                                                    "Talent Workshops",
                                                    "CPSC Certificates",
                                                    "Ratings",
                                                    "Shop Help",
                                                    "Contact Us"
                                                ]
                                },
                                {
                                    list_title  : "SITES",
                                    list        : [
                                                    "DC",
                                                    "MAD Magazine",
                                                    "DC Kids",
                                                    "DC Universe",
                                                    "DC Power Visa"
                                                ]
                                },
                ],
                social_icons: [
                    "footer-facebook.png",
                    "footer-twitter.png",
                    "footer-youtube.png",
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
        <div id="footer_menu_box" class="centered_block">
            <div>
                <ul id="lists_list">
                    <li v-for="(item, list_index) in footer_menus" :key="list_index">
                        <h5>{{ item.list_title }}</h5>
                        <ul id="menu_list">
                            <li v-for="(menu_item, index) in footer_menus[list_index].list" :key="index + 100">
                                <a href="#">{{ menu_item }}</a>
                            </li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
        <img src="../assets/img/dc-logo-bg.png">
        <div id="footer_bottom">
            <div id="sign_up_and_social" class="centered_block">
                <h4 id="cta">SIGN-UP NOW!</h4>
                <div id="social_flex">
                    <h4>FOLLOW US</h4>
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

    #footer_box{
        min-height: $footer_bg_height;
        background-image: url("../assets/img/footer-bg.jpg");
        position: relative;
        #footer_menu_box{
            height: calc(100% - $footer_height);
            div{
                width: 33%;
                padding: auto 0;
                #lists_list{
                    max-height: calc($footer_bg_height - $footer_height);

                    display: flex;
                    flex-flow: column wrap;
                    gap: 1rem;
                    color: white;
                    li{
                        h5{
                            margin: 1rem 0;
                        }
                        #menu_list{
                            @include itemsListStyle(3, 0.7rem, 10px, rgb(186, 178, 178));
                            li{
                                &:hover{
                                    a{
                                        color: lightblue;
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
        img{
            height: calc(100% + $footer_height);
            position: absolute;
            bottom: 0;
            left: 50%;
        } 
        #footer_bottom{
            position: absolute;
            bottom: 0;
            z-index: 999;
            width: 100%;
            height: $footer_height;
            background-color: $footer_color;
            #sign_up_and_social{
                height: 100%;
                display: flex;
                justify-content: space-between;
                align-items: center;
                    h4#cta{
                        color: white;
                        padding: 0.75rem;
                        border: 3px solid blue;
                        cursor: pointer;
                        &:hover{
                            color: $central_color;
                        }
                    } 
                    #social_flex{
                        height: 100%;
                        display: flex;
                        align-items: center;
                        gap: 1rem;
                        h4{
                            margin: 0 2rem;
                            color: $central_color;
                        }
                        div{
                            position: relative;
                            height: 50%;
                            aspect-ratio: 1;
                            img{
                                position: absolute;
                                top: 50%;
                                left: 50%;
                                transform: translate(-50%, -50%);
                                width: 100%;
                                object-fit: contain;
                                cursor: pointer;
                            } 
                        } 
                    } 
            }
        }
    }
</style>