<template>
  <div class="item">
    <img :src="product.img" :alt="product.title">
    <router-link :to="/shop/ + product.id" class="link"> {{product.title}}</router-link>
    <div class="buy">
        <button class="btn btn-primary">Купить</button>
    </div>
    
  </div>
</template>

<script>
export default {
    props: {
        product: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang='scss'>
.item__wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
}
.item {
    max-width: 48%;
    text-align: center;
    p {
        font-size: 22px;
    }
}

.btn {
    margin-top: 10px;
    transition: all .1s ease-in;
}

.btn:hover {
    transform: scale(1.2);
}


</style>