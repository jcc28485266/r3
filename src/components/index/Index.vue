<template>
  <div>
    <div class="content">
      <router-view></router-view>
    </div>
    
    <div class="tool-bar-container">
      <ul class="tool-bar">
        <li>
          <router-link to="/home">
            <p>Home</p>
            <p>
                <span class="iconfont"
                      :class="(getRoutePath=='/home')?'icon-home1':'icon-home'"></span>
              <!--<span class="iconfont icon-home1"></span>-->
            </p>
          </router-link>
        </li>
        <li>
          <router-link to="/cate">
            <p>Cate</p>
            <p><span>图2</span></p>
          </router-link>
        </li>
        <li>
          <p>Order</p>
          <p><span>图3</span></p>
        </li>
        <li>
          <p>Profile</p>
          <p><span>图4</span></p>
        </li>
      </ul>
    </div>
  </div>


</template>

<script>
  import Vue from 'vue'
  import VueRouter from 'vue-router'
  import Home from "@/components/home/Home";
  import Cate from "@/components/cate/Cate";
  import Order from "@/components/order/Order";
  import Profile from "@/components/profile/Profile";

  Vue.use(VueRouter)

  const routes = [
    {
      path: '/',
      component: Home
    }, {
      path: '/Home',
      component: Home
    }, {
      path: '/Cate',
      component: Cate
    }, {
      path: '/Order',
      component: Order
    }, {
      path: '/Profile',
      component: Profile
    }
  ];

  const router = new VueRouter({routes});

  export default {
    name: "Index",
    router: router,
    computed: {
      getRoutePath() {
        return this.$route.path;
      }
    }
  }
</script>

<style scoped>
  .tool-bar-container {
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
  }
  
  .tool-bar {
    display: flex;
    background-color: #CCCCCC;
    border-top: 1px solid #9c9c9c;
  }
  
  .tool-bar li {
    flex: 1;
    text-align: center;
  }
  
  .router-link-active {
    color: red;
  }
</style>
