<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section>
        <div class="container">
           
            
            
        </div>
    </section>
  </div>
</template>

<script>
import shopItem from '@/components/ShopItem.vue'
export default {
  components: {
    shopItem
  },
  data () {
    return {
      shopList: null
    }
  },
  methods: {
   addToCart(data) {
   console.log(data)
   }
  },
   created () {
    this.shopList = this.$store.getters.getShopList
  },
}
</script>

<style>

</style>