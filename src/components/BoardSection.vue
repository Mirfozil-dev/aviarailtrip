<template>
  <div :class="section.active ? 'active' : ''" class="boards_bar__section">
    {{ section.title }}
  </div>
</template>

<script>
export default {
  name: 'BoardSection',
  props: {
    section: Object,
  },
};
</script>

<style scoped>

.boards_bar__section {
  height: 44px;
  display: flex;
  align-items: center;
  padding: 0 12px;
  border-radius: 10px;
  margin-bottom: 20px;
}

.boards_bar__section.active {
  color: #0F6AC2;
  background: #E7F6FF;
}
</style>