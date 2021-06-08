<template>
    <div class="container">
        <p class="h1 text-primary text-center my-3">Дополнительные сведения</p>
        <div class="card">
            <img :src="hero.img" class="card-img-left" :alt="hero.name">
            <div class="card-body">
                <ul class="list-group list-group-flush">
                    <li class="list-group-item">Name: <strong>{{hero.name}}</strong></li>
                    <li class="list-group-item">Nickname: <strong>{{hero.nickname}}</strong></li>
                    <li class="list-group-item">Date of birth: <strong>{{hero.birthday}}</strong></li>
                    <li class="list-group-item">Status: <strong>{{hero.status}}</strong></li>
                    <li class="list-group-item">Actor: <strong>{{hero.portrayed}}</strong></li>
                    <li class="list-group-item">Appearance in seasons: <strong>
                        <span v-for="(el, index) in hero.appearance" :key="index">{{el+" "}}</span></strong></li>
                </ul>
            </div>

        </div>

    </div>
</template>

<script>
export default {
    async asyncData({$axios, params}){
        const heroes = await $axios.$get("https://www.breakingbadapi.com/api/characters/"+params.id);
        const hero = heroes[0];
        console.log(hero);
        return {hero};
    }
}
</script>

<style lang="scss" scoped>
.card {
    display: flex;
    flex-direction: row;
    .card-img-left {
        width: 300px;
    }
}
</style>