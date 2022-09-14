<template>
   <div class="wrapper-content wrapper-content--fixed">
    <section>
        <div class="container">
            <h1>Shop Page</h1>
            <div class="item__wrapper">
            <shopItem 
            v-for="product in shopList" :key="product.id"
            :product="product"
            @addToCart="addToCart"
            />
            </div>
        </div>
    </section>

     <section>
        <div class="container">
            <div class="item__wrapper">
           <cartWrapper v-if="CART.length" />
            </div>
        </div>
    </section>
  </div>
</template>

<script>
import shopItem from '@/components/ShopItem.vue'
import cartWrapper from '@/components/Cart-Wrapper.vue'
import {mapGetters} from 'vuex'
export default {
  components: {
    shopItem,
    cartWrapper
  },
  data () {
    return {
      shopList: null
    }
  },
  computed: {
    ...mapGetters([
      'CART',
      'ADD_TO_CART'
    ])
  },
  created () {
    this.shopList = this.$store.getters.getShopList
  },
  methods: {
    addToCart(data) {
      this.ADD_TO_CART(data)
    }
    },
  }

</script>

<style>

</style>