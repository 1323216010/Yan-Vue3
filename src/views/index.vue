<template>
  <div class="link">

    <el-link class="box" style="font-size: 2em;" @click="toFileReview">小说阅读</el-link>
  </div>
</template>

<script>

export default {
name: "Login",
data() {
  return {
    user: {},

  }
},
methods: {
  toFileReview() {
    this.$router.push('/novel')
  }

}
}
</script>