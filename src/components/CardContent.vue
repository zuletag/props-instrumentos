<template>
    <div class="CardContent">
        <div :style="{backgroundImage: `url(${foto})`}" class="imgSrc"></div>
        <slot/>
    </div>
</template>

<script>
export default {
    props:["foto"]
}
</script>

<style scoped>
.CardContent {
    text-align: center;
    width: fit-content;
}

.imgSrc {
    background-image:
        url("https://avatars.githubusercontent.com/u/499550?v=4");
    background-size: cover;
    background-position: center;
    height: 200px;
    width: 400px;
    margin-bottom: 20px;
}
</style>