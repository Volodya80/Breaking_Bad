<template>
    <div class="container-fluid">
        <p class="h3 text-center">Содержание</p>
        <ul class="list-group">
            <li class="list-group-item"
                v-for="(el,key) in menuItems" v-bind:key="key">
                    <nuxt-link :to="el.adress" >
                        {{ el.menuItem }}
                    </nuxt-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedItem: 0,
            menuItems: [
                {menuItem: 'О проекте',             adress: "/about"},
                {menuItem: 'О сериале',             adress: "/"},
                {menuItem: 'Герои',                 adress: "/"},
                {menuItem: 'Актерский состав',      adress: "/"},
                {menuItem: 'Съемочная группа',      adress: "/"},
                {menuItem: 'Фотогалерея',           adress: "/"},
                {menuItem: '20 фактов о сериале',   adress: "/"}
            ]
        }
    }
}
</script>

<style lang="scss">
    //@import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');

    
   
</style>