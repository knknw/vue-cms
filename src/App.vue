


<template >
  <!--这是vue组件模板的页面 主要存放组件渲染的页面代码
    应为顶部和底部不变所以直接用组件渲染出来,中间是根据底部按钮改变的,所以
    用路由做相应的切换
   -->
  <div class="app-conpen" >
  
  
    <!-- 顶部Header区域 -->
    <mt-header fixed title="Vue实战经典">
        <span 
      v-show="$route.path !== '/home'" 
      @click="$router.go(-1)" 
      slot="left">
        <mt-button icon="back">返回</mt-button>
        </span>
    </mt-header>
    <!-- 添加动画 -->
    <transition>
       <router-view></router-view>
    </transition>
  
    <!-- 底部Tabbar区域 -->
    <nav class="mui-bar mui-bar-tab">
      <router-link class="mui-tab-item" to="/home">
        <span class="mui-icon mui-icon-home"></span>
        <span class="mui-tab-label">首页</span>
      </router-link>
      <router-link class="mui-tab-item" to="/member">
        <span class="mui-icon mui-icon-contact"></span>
        <span class="mui-tab-label">会员</span>
      </router-link>
      <router-link class="mui-tab-item" to="/shopcar">
        <span class="mui-icon mui-icon-extra mui-icon-extra-cart" id="sdfr"> 
          <span class="mui-badge">{{$store.getters.gettoallcoente }}</span>
        </span>
        <span class="mui-tab-label">购物车</span>
      </router-link>
      <router-link class="mui-tab-item" to="/search">
        <span class="mui-icon mui-icon-search"></span>
        <span class="mui-tab-label">搜索</span>
      </router-link>
    </nav>
    
    
  </div>
</template>

<script>
  
</script>

<style lang="less" scoped>
  .app-conpen{
    padding-top: 40px;
     padding-bottom: 50px;
     overflow-x: hidden;
     background-color: #ffffff;
  }
  .v-enter{
    opacity: 0;
    transform:translateX(100%)
  }
  .v-leave-to {
    opacity: 0;
    transform:translateX(-100%);
    position: absolute;
  }
  .v-enter-active,
  .v-leave-active{
    transition: all 0.5s ease;
  }
</style>

