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
                {menuItem: 'О сериале',             adress: "/about"},
                {menuItem: 'Герои и актеры',        adress: "/heroes"},
                {menuItem: 'Цитаты',                adress: "/quotes"},
                {menuItem: 'Фотогалерея',           adress: "/gallery"},
                //{menuItem: '20 фактов о сериале',   adress: "/"},
                {menuItem: 'На главную',            adress: "/"}
            ]
        }
    }
}
</script>
