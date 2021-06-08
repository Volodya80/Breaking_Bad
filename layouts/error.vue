<template>
    <div class="container box-outer">
        <div class="box-inner">
            <p class="h1 text-center text-danger">ERROR 404</p>
            <p class="h2 text-center text-secondary">Страница не нейдена</p>
            <p class="h3 text-center text-primary">
                <nuxt-link to="/">Home</nuxt-link>
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.box-outer {
    position: relative;
    height: 90vh;  

    .box-inner {
        position: relative;
        top: 50%;
        transform: translateY(-50%);
        margin: auto;
    }  
}
</style>

<script>
export default {
    layout: "empty"
}
</script>