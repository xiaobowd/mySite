<template>
  <div id="app">
    <el-container>
      <el-header>
        <v-header />
      </el-header>
        <el-main>
          <router-view></router-view>
        </el-main>
      <el-footer>
        <v-footer />
      </el-footer>
    </el-container>
  </div>
</template>

<script>
import NavMenu from '@/components/NavMenu'
import Header from '@/components/Header'
import Footer from '@/components/Footer'
export default {
  name: 'app',
  components: {
    NavMenu: NavMenu,
    VHeader: Header,
    VFooter: Footer
  }
}
</script>

<style scoped>
</style>
