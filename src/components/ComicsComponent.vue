<script>
    import SingleCardViewer from "./SingleCardViewer.vue"
    export default{
        name:   "ComicsComponent",
        components: {
            SingleCardViewer
        },
        data()
        {
            return{
                active_item : 0,
                comics      : [
                {
                    thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
                    price: "$19.99",
                    series: "Action Comics",
                    type: "comic book",
                },
                {
                    thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
                    price: "$3.99",
                    series: "American Vampire 1976",
                    type: "comic book",
                },
                {
                    "thumb": "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
                    "price": "$16.99",
                    "series": "Aquaman",
                    "type": "graphic novel",
                },
                {
                    "thumb": "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
                    "price": "$2.99",
                    "series": "Batgirl",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
                    "price": "$3.99",
                    "series": "Batman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
                    "price": "$2.99",
                    "series": "Batman Beyond",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
                    "price": "$3.99",
                    "series": "Batman/Superman",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
                    "price": "$4.99",
                    "series": "Batman/Superman Annual",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
                    "price": "$5.99",
                    "series": "Batman: The Joker War Zone",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
                    "price": "$6.99",
                    "series": "Batman: Three Jokers",
                    "type": "comic book",
                },
                {
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
                    "price": "$4.99",
                    "series": "Batman: White Knight Presents: Harley Quinn",
                    "type": "comic book",
                },
                {           
                    "thumb": "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
                    "price": "$16.99",
                    "series": "Catwoman",
                    "type": "graphic novel",
                }
                ] 
            }
        }
    }
</script>

<template>
    <div id="comics_area">
        <div id="floating_label">
            <span>CURRENT SERIES</span>
        </div>
        <div id="cards_container" class="centered_block">
            <div class="comics_card" v-for="(card, index) in comics" :key="index">
                <SingleCardViewer :single_card = "card" />
            </div>
        </div>
        <div id="load_more">
            <a href="#">LOAD MORE</a>
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;

    #comics_area{
        position: relative;
        min-height: $comics_area_height;
        background-color: $comics_bg_color;
        padding: 3rem 0;
        #floating_label{
            width: 200px;
            background-color: $central_color;
            padding: 10px 25px;
            color: white;
            position: absolute;
            top: 0;
            left: calc((100% - $block_width) / 2);
            transform: translate(-15px, -50%);
        }
        #cards_container{
            display: flex;
            flex-wrap: wrap;
            gap: $cards_gap;
            .comics_card{
                flex-basis: calc((100% - ($cards_gap * ($cards_per_row - 1))) / $cards_per_row);
                overflow: hidden;
                cursor: pointer;
                border: 3px solid $comics_bg_color;
                &:hover{
                    border-color: blue;
                }
            }
        }
        #load_more{
            width: 150px;
            background-color: $central_color;
            padding: 10px 25px;
            margin: 0 auto;
            margin-top: 2rem;
            a{
                color: white;
                &:hover{
                    color: yellowgreen;
                }
            }
        }
    }
</style>