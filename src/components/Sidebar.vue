<template>
  <div class="sidebar_wrapper">
    <img class="sidebar_logo" src="@/assets/logo.svg" alt="">
    <div class="sidebar_items_wrapper">
      <sidebar-item v-for="(item, index) in sidebarLinks" :key="index" :item="item" />
    </div>
  </div>
</template>

<script>
import SidebarItem from './SidebarItem.vue';

export default {
  name: 'Sidebar',
  components: { SidebarItem },
  data() {
    return {
      sidebarLinks: [
        {
          icon: 'ri-home-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-contacts-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-money-dollar-circle-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-ticket-2-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-file-list-3-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-folder-open-line',
          url: '#',
          active: true,
        },
        {
          icon: 'ri-user-follow-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-line-chart-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-file-user-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-pie-chart-line',
          url: '#',
          active: false,
        },
        {
          icon: 'ri-file-chart-line',
          url: '#',
          active: false,
        },
      ],
    };
  },
};
</script>

<style scoped>
.sidebar_wrapper {
  max-width: 60px;
  width: 100%;
  height: 100vh;
  background: #FFFFFF;
  border-right: 1px #EAF1F8 solid;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 2;
}

.sidebar_logo {
  width: 27px;
  height: 30px;
  object-fit: contain;
  margin-top: 24px;
}

.sidebar_items_wrapper {
  margin-top: 34px;
  display: flex;
  flex-direction: column;
}
</style>