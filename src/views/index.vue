<template>
  <div>

  </div>
</template>

<script>
import { reactive, toRefs, onMounted } from "vue";
import { useRouter, useRoute } from "vue-router";

export default {
  name: "Navbar",
  setup() {
    const route = useRoute();
    const router = useRouter();

  },
};
</script>
