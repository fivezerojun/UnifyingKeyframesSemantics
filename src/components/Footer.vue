<script lang="ts" setup>
const links = {
  vue: "https://vuejs.org/",
  vite: "https://vitejs.dev/",
  elementPlus: "https://element-plus.org/",
}
</script>

<template>
  <footer class="footer-bg">
    <el-row justify="center">
      <p class="footer">
        Unifying Precise Keyframes and Semantic Control via Multi-level Diffusion<br/>
        Powered by
        <a :href="links.vue">Vue</a>,
        <a :href="links.vite">Vite</a>, and
        <a :href="links.elementPlus">Element Plus</a>.
      </p>
    </el-row>
  </footer>
</template>

<style scoped>
.footer-bg {
  background-color: rgb(245, 245, 245);
}

.footer {
  color: #606266;
  line-height: 1.7;
  margin: 24px;
  text-align: center;
  z-index: 1;
}

a {
  color: inherit;
}
</style>
