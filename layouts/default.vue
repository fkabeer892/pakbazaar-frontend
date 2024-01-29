<template>
  <div id="layout">
    <a-layout>
      <a-layout-sider
        breakpoint="lg"
        collapsed-width="0"
        class="bg-white layout-sidebar"
        :inline-collapsed="true"
        @collapse="onCollapse"
        @breakpoint="onBreakpoint"
      >
        <Sidebar />
      </a-layout-sider>
      <a-layout class="main-layout">
        <a-layout-header class="layout-header">
          <Header />
        </a-layout-header>
        <a-layout-content>
          <div class="layout-content">
            <Nuxt />
          </div>
        </a-layout-content>
        <a-layout-footer>
          <Footer />
        </a-layout-footer>
      </a-layout>
    </a-layout>
  </div>
</template>
<script>
import Header from '@/components/Layout/Header'
import Sidebar from '@/components/Layout/Sidebar'
import Footer from '@/components/Layout/Footer'

export default {
  components: {
    Header,
    Sidebar,
    Footer,
  },
  methods: {
    onCollapse(collapsed, type) {
      console.log(collapsed, type)
    },
    onBreakpoint(broken) {
      console.log(broken)
    },
  },
}
</script>

<style lang="scss">
@import '@/assets/global/layouts/baseLayout';
</style>
