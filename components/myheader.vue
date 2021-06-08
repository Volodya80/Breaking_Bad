<template>
    <div class="head-container">
        <div class="left-container"></div>
        <div class="right-container"></div>
    </div>
</template>

<style lang="scss" scoped>
.head-container {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: stretch;
    height: 100%;
    background-color: black;
    .left-container {
        width: 50%;
        background-image: url('@/assets/img/Breaking_Bad_logo.svg');
        background-repeat: no-repeat;
        background-position: top left;
        background-size: contain;
    }
    .right-container {
        width: 50%;
        padding-left: 5px;
        background-image: url('@/assets/img/header_img_0.png');
        background-position: top right;
        background-repeat: no-repeat;
        background-size: contain;
    }
}
</style>