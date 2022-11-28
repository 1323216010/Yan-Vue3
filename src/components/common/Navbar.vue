<template>
  <div class="mainNav" id="mainNav">
    <div class="box_center cf">
      <ul class="nav" id="navModule">
        <li><router-link :to="{ name: 'novel' }">首页</router-link></li>
        <li>
          <router-link :to="{ name: 'novel' }"> 全部作品 </router-link>
        </li>
        <li><router-link :to="{ name: 'novel' }">排行榜</router-link></li>
        <!--<li class=""><a href="/pay/index.html">充值</a></li>-->
        <li><a @click="goAuthor" href="javascript:void(0)">作家专区</a></li>
      </ul>
    </div>
  </div>
</template>
  
<script>
import Top from "@/components/common/Top";
import logo from "@/assets/images/logo.png";
import { reactive, toRefs, onMounted } from "vue";
import { useRouter, useRoute } from "vue-router";
import "@/assets/styles/base.css";
export default {
  name: "Navbar",
  setup() {
    const route = useRoute();
    const router = useRouter();
    return {

      logo,

    };
  },
};
</script>