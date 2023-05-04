<script>
    export default{
        name: "NavMenu",
        data()
        {
            return{
                active_item: 0,
                main_menu : [
                    {text: "CHARACTERS"},
                    {text: "COMICS"},
                    {text: "MOVIES"},
                    {text: "TV"},
                    {text: "GAMES"},
                    {text: "COLLECTIBLES"},
                    {text: "VIDEOS"},
                    {text: "FANS"},
                    {text: "NEWS"},
                    {text: "SHOP"}
                ]
            }
        },
        methods:{
            set_active(index)
            {
                this.active_item = index;
            }
        }
    }
</script>

<template>
    <nav>
        <ul>
            <li v-for="(item, index) in main_menu" :key="index" v-bind:class="(index == active_item) ? ('active') : ('')">
                <div>
                    <a href="#" v-on:click="set_active(index)">{{item.text}}</a>
                </div>
            </li>
        </ul>
    </nav>
</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;
    nav
    {
        ul
        {
            @include itemsListStyle(1, 0.6rem, 25px, black);
            li
            {
                border-bottom: $menu_border_thickness solid white;
                div
                {
                    height: 100%;
                    margin: 0;
                    padding: 0;
                    line-height: $header_height;
                } 
            } 
        }
    }
</style>