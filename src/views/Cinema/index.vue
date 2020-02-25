<template>
  <div>
    <me-header title="喵喵影院"></me-header>
    <me-tab-bar class="bg-gray ai-center border-bottom" :class="$style.top_bar">
      <template v-slot:left>
        <div :class="$style.city_entry">
          <span class="text-light-gray">佛山</span>
          <i class="iconfont icon-xiasanjiaoxing text-light-gray fs-8"></i>
        </div>
      </template>

      <template v-slot:center>
        <div :class="$style.search_input" class="flex-1 bg-white text-center">
          <i class="iconfont icon-sousuo"></i>
          <span>搜影院</span>
        </div>
      </template>
    </me-tab-bar>

    <me-tab-bar class="border-bottom" :class="$style.nav_wrap">
      <template v-slot:center>
        <ul class="d-flex text-gray fs-13 text-center" :class="$style.nav_filter">
          <li class="flex-1 text-gray">
            <span>全城</span>
            <i class="iconfont icon-xiasanjiaoxing fs-8"></i>
          </li>
          <li class="flex-1 text-gray">
            <span>品牌</span>
            <i class="iconfont icon-xiasanjiaoxing fs-8"></i>
          </li>
          <li class="flex-1 text-gray">
            <span>特色</span>
            <i class="iconfont icon-xiasanjiaoxing fs-8"></i>
          </li>
        </ul>
      </template>
    </me-tab-bar>

    <me-tab-bar :class="$style.footer" class="w-100 border-top">
      <ul class="d-flex h-100 ai-center text-center" slot="center">
        <router-link tag="li" to="/movie" class="flex-1">
          <i class="iconfont icon-dianying fs-l"></i>
          <p class="fs-sm">电影</p>
        </router-link>
        <router-link tag="li" to="/cinema" class="flex-1">
          <i class="iconfont icon-huabankaobei fs-l"></i>
          <p class="fs-sm">影院</p>
        </router-link>
        <router-link tag="li" to="/mine" class="flex-1">
          <i class="iconfont icon-wode fs-l"></i>
          <p class="fs-sm">我的</p>
        </router-link>
      </ul>
    </me-tab-bar>
  </div>
</template>

<script>
import MeHeader from "@/base/Header";
import MeTabBar from "@/base/TabBar";
export default {
  name: "Cinema",
  components: {
    MeHeader,
    MeTabBar
  }
};
</script>

<style lang="scss" module>
@import "~@/assets/scss/variable.scss";
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  li {
    padding: 8px 0 4px 0;
  }
  p {
    line-height: map-get($map: $font-sizes, $key: "18") * $base-font-size;
  }
}
.search_input {
  border-radius: 5px;
  border: 1px solid map-get($map: $colors, $key: "light-white");
  margin: 10px 15px 10px 18px;
  padding: 5px 0;
}

.city_entry{
  padding-left: 15px;
}

.nav_filter,.city_entry{
  i{
    position: relative;
    left: 5px;
    top: -2px;
  }
}

.nav_filter>li{
  position: relative;
}

.nav_filter>li:not(:first-child)::after{
  content: '';
  height: 20px;
  display: block;
  position: absolute;
  top: 0px;
  left: 0;
  border-left: 1px solid #e8e8e8;
}

.nav_wrap{
  padding: 10px 0;
}
</style>

<style lang="scss">
@import "~@/assets/scss/variable.scss";
li.router-link-active {
  color: map-get($map: $colors, $key: "light-red");
}
</style>