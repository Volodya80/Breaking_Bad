<template>
    <div class="menu-area">
        <p class="h2 text-center">Содержание</p>
        <ul class="nav-bar navbar-dark bg-dark">
            <li v-for="(el,key) in menuItems" v-bind:key="key" class="nav-item">
                <nuxt-link :to="el.adress" class-active="active">
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
    @import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');

    
    $txt-color: #a3eb87;
    $txt-color-hover: #FFFFFF;

    .menu-area {

        //background-color: $bk-color;
        color: $txt-color;

        font-family: 'Rubic', sans-serif;

        margin: 5px 5px;
        ul {
            li {
                cursor: pointer;
            }
            li:hover {
                color: $txt-color-hover;
            }
        }

        .active {
            color: yellow;
        }
    }
</style>