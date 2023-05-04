<script>
    export default{
        name    : "NavMenu",
        data(){
            return{
                active_item : 0,
                main_menu   : [
                    {
                        text    : "CHARACTERS",
                        link    : "#"
                    },
                    {
                        text    : "COMICS",
                        link    : "#"
                    },
                    {
                        text    : "MOVIES",
                        link    : "#"
                    },
                    {
                        text    : "TV",
                        link    : "#"                    
                    },
                    {
                        text    : "GAMES",
                        link    : "#"                    
                    },
                    {
                        text    : "COLLECTIBLES",
                        link    : "#"                    
                    },
                    {
                        text    : "VIDEOS",
                        link    : "#"                    
                    },
                    {
                        text    : "FANS",
                        link    : "#"                    
                    },
                    {
                        text    : "NEWS",
                        link    : "#"                    
                    },
                    {
                        text    : "SHOP",
                        link    : "#"                    
                    }
                ]
            }
        },
        methods :{
            set_active(index)
            {
                this.active_item = index;
            }
        }
    }
</script>

<template>
    <header>
        <div class="centered_block">
            <img src="../assets/img/dc-logo.png" alt="logo piccolo">
            <nav>
                <ul>
                    <li 
                    v-for="(item, index) in main_menu" :key="index" v-bind:class="(index == active_item) ? ('active') : ('')">
                        <a v-bind:href="(item.link)" v-on:click="set_active(index)">{{item.text}}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>

</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;

    header{
        height: $header_height;
        background-color: white;
        div.centered_block{
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
            img{
                height: 90%;
            }
            nav{
                height: 100%;
                ul{
                    height: 100%;
                    @include itemsListStyle(1, 0.6rem, 25px, black);
                    li{
                        height: 100%;
                        display: flex;
                        align-items: center;
                        border-bottom: $menu_border_thickness solid transparent;
                        a{
                            font-weight: 800;
                        } 
                        &.active{
                            border-color: blue;
                            a{
                                color: blue;
                            }
                        }
                    } 
                }
            }
        }
    }

</style>