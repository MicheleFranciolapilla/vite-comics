<script>
    export default{
        name: "NavMenu",
        data()
        {
            return{
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
        }
    }
</script>

<template>
    <nav>
        <ul>
            <li v-for="(item, index) in main_menu" :key="index">
                <a href="/">{{item.text}}</a>
            </li>
        </ul>
    </nav>
</template>

<style lang="scss">
    @use "../style/main.scss" as *;
    nav{
        ul{
            @include itemsListStyle(1, 0.75rem, 20px, black);
        }
    }
</style>