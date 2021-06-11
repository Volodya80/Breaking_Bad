<template>
    <div class="container">
        <p class="h1 text-primary text-center">Фотогалерея</p>
        <div class="cards-area">
            <div class="card" v-for="i in count" :key="i" >
                <img :src="pict[i]" class="card-img-top" :alt="pict" @click="showPict(i)">
            </div>
        </div>
        <button class="btn btn-primary my-2 mx-auto" @click="addPhotos">Показать еще 10</button>
        <a href="#" class="upBtn" v-show="scrolled">Наверх</a>
        <div class="bigImage" v-show="visiblePicture">
            <img :src="pict[activePicture]" alt="active picture" @click="showPict(1)">
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            pict: [],
            count: 20,
            scrolled: false,
            visiblePicture: false,
            activePicture: 1
        }
    },
    async created() {
        

        const response = await fetch("https://api.kinopoisk.cloud/tv-series/404900/token/20974d2f067ab0c69f34db298535514c");
        const picts = await response.json();
        this.pict = picts["frames"];
        //console.log(picts);
        window.addEventListener('scroll', this.handleScroll);

    },
    methods: {
        addPhotos() {
            this.count += 10;
        },
        handleScroll () {
            this.scrolled = window.scrollY > 50;
        },
        destroyed(){
            window.removeEventListener('scroll', this.handleScroll);
        },
        showPict(No){
            this.activePicture = No;
            this.visiblePicture = !this.visiblePicture;
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    .cards-area {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        align-items: stretch;

        margin: 0 auto;

        .card{
            width: 150px;
            height: 150px;
            margin-top: 2px;

            cursor: pointer;
            >img {
                width: 150px;
                height: 150px;
                top: 0;
                
                object-fit: cover;
                object-position: 20% 10%; /* try 20px 10px */ 
            }
        }
    }
    .upBtn {
        position: fixed;
        bottom: 3%;
        right: 1%;

        padding: 5px;

        text-decoration: none;

        border: 1px solid darkblue;
        border-radius: 3px;
        
        background-color: rgba(0, 0, 255, 0.5);

        color: white;
    }
    .bigImage{
        display: flex;
        align-content: center;

        position: fixed;

        top: 5%;
        left: 5%;

        width: 90%;
        height: 90%;
        margin: auto;

        background-color: rgba(0, 0, 0, 0.8);
        border: 1px solid blue;

        border-radius: 40px;
        >img{
            display: block;

            margin: auto;

            width: inherit;
            height: inherit;

            object-fit: cover;
            object-position: 20% 10%;
        }
    }
}
</style>