<template>
  <div id="layout-sidebar">
    <div class="logo">
      <Logo />
    </div>
    <a-menu
      style="width: 256px"
      :default-selected-keys="['dashboard']"
      :open-keys.sync="openKeys"
      mode="inline"
      @click="handleClick"
    >
      <a-menu-item key="dashboard" class="single-item"
        ><a-icon type="appstore" /> Dashboard
      </a-menu-item>
      <a-sub-menu
        key="user-managment"
        class="sub-item"
        @titleClick="titleClick"
      >
        <span slot="title"
          ><a-icon type="appstore" /><span>User Management</span></span
        >
        <a-menu-item key="admin"> Admins</a-menu-item>
        <a-menu-item key="customer"> Customers </a-menu-item>
        <a-menu-item key="service-workers"> Service Workers </a-menu-item>
      </a-sub-menu>
      <a-menu-item key="products" class="single-item"
        ><a-icon type="appstore" /> Products
      </a-menu-item>
      <a-divider></a-divider>
      <a-menu-item-group key="categories" class="px-2">
        <template slot="title">
          <span>Categories</span>
        </template>
      </a-menu-item-group>

      <a-menu-item key="product-category" class="single-item"
        ><a-icon type="appstore" /> Products
      </a-menu-item>
      <a-menu-item key="service-category" class="single-item"
        ><a-icon type="appstore" /> Services
      </a-menu-item>
    </a-menu>
  </div>
</template>
<script>
import Logo from '@/components/Logo'
export default {
  components: {
    Logo,
  },
  data() {
    return {
      current: ['dashboard'],
      openKeys: ['user-managment'],
    }
  },
  watch: {
    openKeys(val) {
      console.log('openKeys', val)
    },
  },
  methods: {
    handleClick(e) {
      console.log('click', e)
    },
    titleClick(e) {
      console.log('titleClick', e)
    },
  },
}
</script>
