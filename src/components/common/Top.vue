<template>
  <div class="topMain">
    <div class="box_center cf">
      <router-link :to="{ name: 'novel' }" class="logo fl"><img :src="logo" alt="小说精品屋" /></router-link>
      <div class="searchBar fl">
        <div class="search cf">
          <input v-model="keyword" type="text" placeholder="书名、作者、关键字" class="s_int" v-on:keyup.enter="searchByK" />
          <label class="search_btn" id="btnSearch" @click="searchByK()"><i class="icon"></i></label>
        </div>
      </div>
    
      <div class="bookShelf fr" id="headerUserInfo">
        <span v-if="!token" class="user_link">
          <router-link :to="{ name: 'novel' }" class="mr15">登录</router-link>
          <router-link :to="{ name: 'novel' }" class="mr15">注册</router-link>
        </span>
        <span v-if="token" class="user_link">
          <router-link :to="{ name: 'novel' }" class="mr15">{{ nickName }}</router-link>
          <a @click="logout" href="javascript:void(0)">退出</a>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import logo from "@/assets/images/logo.png";
import { reactive, toRefs, onMounted } from "vue";
import { useRouter, useRoute } from "vue-router";
import "@/assets/styles/base.css";
// import '@/assets/styles/main.css'
// import '@/assets/styles/about.css'
// import '@/assets/styles/book.css'
// import '@/assets/styles/easyui.css'
// import '@/assets/styles/layer.css'
// import '@/assets/styles/main.css'
// import '@/assets/styles/read.css'
import '@/assets/styles/user.css'
export default {
  name: "Top",
  setup(props, context) {
    const state = reactive({
      keyword: "",

    });

    const route = useRoute();
    const router = useRouter();
    state.keyword = route.query.key;
    const searchByK = () => {
      router.push({ path: "/bookclass", query: { key: state.keyword } });
      context.emit("eventSerch", state.keyword);
    };
    const logout = () => {
      removeToken();
      removeNickName();
      removeUid()
      state.nickName = "";
      state.token = "";
    };
    return {
      ...toRefs(state),
      logo,
      searchByK,
      logout,
    };
  },
};
</script>

