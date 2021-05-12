<template>
  <div class="boards_bar_wrapper">
    <div>
      <h6>
        Проекты
      </h6>
      <div class="boards_bar__sections">
        <board-section v-for="(item, index) in boards" :key="index" :section="item" />
      </div>
    </div>
    <button :disabled="modal" @click="showModal" class="add_board_btn">Создать доску</button>
  </div>
</template>

<script>
import BoardSection from './BoardSection.vue';

export default {
  name: 'BoardsBar',
  components: { BoardSection },
  props: {
    modal: Boolean,
  },
  data() {
    return {
      boards: [
        {
          title: 'Доски',
          active: true,
        },
        {
          title: 'Тикеты',
          active: false,
        },
      ],
    };
  },
  methods: {
    showModal() {
      this.$emit('showmodal');
    },
  },
};
</script>

<style scoped>
.boards_bar_wrapper {
  max-width: 209px;
  width: 100%;
  height: 100vh;
  background: #FFFFFF;
  padding: 0 8px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  z-index: 2;
}

.boards_bar_wrapper h6 {
  font-size: 16px;
  font-weight: 600;
  margin: 30px 0 0 12px;
}

.boards_bar__sections {
  margin-top: 28px;
}

.add_board_btn {
  margin-bottom: 24px;
  height: 46px;
  border: none;
  background: #FF6F20;
  font-weight: 600;
  color: #FFFFFF;
  border-radius: 10px;
  transition: .3s;
  cursor: pointer;
}

.add_board_btn:disabled {
  background: #D9E6F2;
  cursor: not-allowed;
}
</style>