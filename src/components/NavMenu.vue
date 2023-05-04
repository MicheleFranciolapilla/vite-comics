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

<style>
</style>