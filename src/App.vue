<template>
  <div class="wrapper">
    <header>
      <div class="navbar">
        <div class="container">
          <div class="navbar-content">
            <div class="logo">VUE-CLI</div>

            <div class="navbar-list">
              <li class="navbar-item" v-for="link in links" :key='link.title'>
                <router-link class="navbar-link" :title="link.title" :to='link.url'> {{link.title}} </router-link>
              </li>
            </div>
          </div>
        </div>
      </div>
    </header>

    <router-view></router-view>


  </div>
</template>

<script>
export default {
  data () {
    return {
      links: [
        {
          title: 'Home',
          url: '/'
        },
          {
          title: 'Shop',
          url: '/shop'
        },
          {
          title: 'Cart',
          url: '/cart'
        }
      ]
    }
  }
};
</script>

<style lang='scss'>
.wrapper {
  background-color: rgb(235, 235, 235);
}
.navbar-link {
  &.router-link-exact-active {
    color: rgb(143, 101, 170);
  }
}
</style>