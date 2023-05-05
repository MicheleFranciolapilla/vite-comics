<script>
    export default{
        name:   "ComicsComponent",
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
        <div id="cards_container" class="centered_block">
            <div class="comics_card" v-for="(card, index) in comics" :key="index">
                <div class="img_container">
                    <img v-bind:src="card.thumb" v-bind:alt="card.series">
                </div>
                <div class="card_info">
                    <h5>{{card.series}}</h5>
                    <h6>{{card.type}}</h6>
                    <h5>{{card.price}}</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;

    #comics_area{
        min-height: $comics_area_height;
        background-color: $comics_bg_color;
        padding: 3rem 0;
        #cards_container{
            border: 3px solid yellow;
            display: flex;
            flex-wrap: wrap;
            gap: $cards_gap;
            .comics_card{
                flex-basis: calc((100% - ($cards_gap * ($cards_per_row - 1))) / $cards_per_row);
                border: 3px solid blue;
                .img_container{
                    width: 100%;
                    aspect-ratio: 1;
                    img{
                    width: 100%;
                    aspect-ratio: 1;
                    object-fit: cover;
                    }
                }
                .card_info{
                    width: 100%;
                    height: 50px;
                    border: 1px solid blueviolet;
                    white-space: nowrap;
                    overflow: clip;
                    // text-overflow: clip;

                    h5,h6{
                        width: calc(100%);
                        white-space: nowrap;
                        overflow: hidden;
                        // text-overflow: clip;
                    }
                }
            }
        }
    }
</style>