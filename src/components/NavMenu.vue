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
                <a href="#" v-on:click="set_active(index)">{{item.text}}</a>
            </li>
        </ul>
    </nav>
</template>

<style lang="scss">
    @use "../style/main.scss" as *;
    nav
    {
        ul
        {
            @include itemsListStyle(1, 0.75rem, 25px, black);
            li
            {
                line-height: calc($header_height - ($menu_border_thickness * 2));
                border-bottom: $menu_border_thickness solid white;
            } 
        }
    }
</style>