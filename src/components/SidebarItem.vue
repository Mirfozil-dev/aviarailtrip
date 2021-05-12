<template>
  <div class="sidebar_item">
    <a :href="item.url">
      <span :class="item.active ? 'active' : ''">
        <i :class="item.icon"></i>
      </span>
    </a>
  </div>
</template>

<script>
export default {
  name: 'SidebarItem',
  props: {
    item: Object,
  },
};
</script>

<style scoped>
.sidebar_item {
  width: 60px;
  height: 50px;
}

.sidebar_item a {
  width: 100%;
  height: 100%;
  text-decoration: none;
  font-size: 25px;
}

.sidebar_item a span {
  width: 44px;
  height: 44px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  color: #283E54;
}

.sidebar_item a span.active {
  background: #E7F6FF;
  color: #0F6AC2;
}

.sidebar_item a span object svg path {
  fill: red !important;
}
</style>