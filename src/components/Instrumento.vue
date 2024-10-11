<template>
    <div class="instrumento">
        <div :style="{backgroundImage: `url(${foto})`}" class="productImg"></div>
        <h2>{{nombre}}</h2>
        <p>{{precio}}</p>
        <button @click="$emit('eliminarInstrumento')">Eliminar</button>
        <slot/>
    </div>
</template>

<script>
export default {
    props:["foto", "nombre", "precio"]
}
</script>

<style scoped>
.instrumento {
    margin-top: 10px;
    text-align: center;
    width: fit-content;
}

.productImg {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(133, 16, 10);
    background-image:
        url("https://avatars.githubusercontent.com/u/499550?v=4");
    background-size: cover;
    background-position: center;
    height: 200px;
    width: 200px;
    border-radius: 50%;
}
</style>