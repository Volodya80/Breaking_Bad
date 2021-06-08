<template>
    <div class="container">
        <p class="text-primary h1 text-center my-3">Heroes and actors</p>
        <div class="cards-area">
            <div class="card" style="width: 18rem;"
                v-for="el in heros" :key="el.char_id">
                <img :src="el.img" class="card-img-top" :alt="el.name">
                <div class="card-body">
                    <a href="#" @click.prevent="getMoreInfo(el)"
                        class="card-title h5 text-center"> {{el.name}}</a>
                </div>
            </div>
        </div>
        <a href="#" class="upBtn">Наверх</a>
    </div>
</template>

<style lang="scss" scoped>
.container {
    .cards-area {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        align-items: stretch;

        margin: 0 auto;

        .card{
            >img {
                height: 300px;
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
        
        background-color: blue;

        color: white;
    }
}
</style>

<script>
export default {
    data() {
        return {
            heros: []
        }
    },
    async created(){
        await this.getHeros();
    },
    methods: {
        async getHeros() {
            let response = await fetch("https://www.breakingbadapi.com/api/characters/");
            let data = await response.json();
            console.log(data);
            for (let i in data) {
                this.heros.push(data[i]);
            }
        },
        getMoreInfo(hero){
            this.$router.push('/heroes/'+hero.char_id);
        }
    }
}
</script>