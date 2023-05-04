<script>
    export default{
        name: "CentralMenu",
        data()
        {
            return{
                active_item: 0,
                central_menu : [
                    {
                        text: "DIGITAL COMICS",
                        img: "buy-comics-digital-comics.png"
                    },
                    {
                        text: "DC MERCHANDISE",
                        img: "buy-comics-merchandise.png"
                    },                    
                    {   
                        text: "SUBSCRIPTION",
                        img: "buy-comics-subscriptions.png"
                    },                    
                    {   
                        text: "COMIC SHOP LOCATOR",
                        img: "buy-comics-shop-locator.png"
                    },                    
                    {
                        text: "DC POWER VISA",
                        img: "buy-dc-power-visa.svg"
                    }
                ]
            }
        },
        methods:
        {
            getImagePath: function(imgPath)
            {
                return new URL(imgPath, import.meta.url).href;
            },

            set_active(index)
            {
                this.active_item = index;
            }
        }
    }
</script>

<template>
    <div id="central_menu_block">
        <ul class="centered_block">
            <li v-for="(item, index) in central_menu" :key="index" v-bind:class="(index == active_item) ? ('active') : ('')">
                <div>
                    <img :src="getImagePath(`../assets/img/${item.img}`)">
                    <a href="#" v-on:click="set_active(index)">{{item.text}}</a>
                </div>
            </li>
        </ul>
    </div>
</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;

    ul
    {
        @include itemsListStyle(2, 0.8rem, 30px, white);
        padding: 0 15px;
        li
        {
            height: 100%;
            div
            {
                cursor: pointer;
                display: flex;
                align-items: center;
                gap: 10px;
                img
                {
                    height: calc($header_height / 1.75);
                    object-fit: contain;
                } 
            } 
            &:hover
            {
                a
                {
                    color: yellow;
                } 
            }
        } 
    }
</style>

