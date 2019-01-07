<template>
<el-container>
  <el-header><Navbar/></el-header>
  <el-main><nuxt/></el-main>
  <el-footer><Footer/></el-footer>
</el-container>
</template>


<script>
import Navbar from '~/components/Navbar.vue';
import Footer from '~/components/Footer.vue';

export default {
  components: {
    Navbar,
    Footer
  }
}
</script>