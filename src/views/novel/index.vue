<template>
  <div class="header">
    <Top />
    <Navbar />
  </div>
</template>

<script>
import Navbar from "@/components/common/Navbar";
import Top from "@/components/common/Top";
export default {
  name: "novel",
  components: {
    Navbar,
    Top,
  },
};
</script>