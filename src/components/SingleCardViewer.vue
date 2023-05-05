<script>
    export default{
        name: "SingleCardViewer",
        props: ['single_card']
    }
</script>

<template>
    <div id="sub_component">
        <div class="img_container">
            <img v-bind:src="single_card.thumb" v-bind:alt="single_card.series">
        </div>
        <div class="card_info">
            <h6>{{single_card.series}}</h6>
            <h6>{{single_card.type}}</h6>
            <span>{{single_card.price}}</span>
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use "../style/main.scss" as *;

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
        width: calc(100%);
        height: 50px;
        padding: 3px 10px;
        border: 1px solid white;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        *{
            width: calc(100%);
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        h6{
            color: yellowgreen;
            &:first-child{
                color: rgb(227, 220, 220);
            }
        }
        span{
            font-size: medium;
            color: blue;
        }
    }
</style>