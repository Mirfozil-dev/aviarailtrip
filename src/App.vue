<template>
  <div id="app">
    <sidebar />
    <boards-bar :modal="modalActive" @showmodal="showModal" />
    <div class="content">
      <div class="control_btns_wrapper">
        <div class="control_btns">
          <button v-for="(item, index) in controlBtns" :key="index">
            <i :class="item.icon"></i>
          </button>
        </div>
      </div>
      <div class="board_cards_row">
        <board-card class="board_card_wrapper" v-for="(item, index) in boardCards" :key="index"
                    :card="item" />
        <div @click="showModal" class="board_card_wrapper">
          <add-board-card />
        </div>
      </div>
    </div>
    <modal @hidemodal="hideModal" :active="modalActive" />
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue';
import BoardsBar from './components/BoardsBar.vue';
import BoardCard from './components/BoardCard.vue';
import AddBoardCard from './components/AddBoardCard.vue';
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: {
    Modal,
    AddBoardCard,
    BoardCard,
    BoardsBar,
    Sidebar,
  },
  data() {
    return {
      controlBtns: [
        {
          icon: 'ri-settings-3-line',
        },
        {
          icon: 'ri-notification-4-line',
        },
        {
          icon: 'ri-account-circle-line',
        },
      ],
      boardCards: [
        {
          title: 'PayFly Design',
          section: 'Дизайн',
          date: '10.10.2020',
        },
        {
          title: 'PayFly Design',
          section: 'Дизайн',
          date: '10.10.2020',
        },
        {
          title: 'PayFly Design',
          section: 'Дизайн',
          date: '10.10.2020',
        },
      ],
      modalActive: false,
    };
  },
  methods: {
    showModal() {
      this.modalActive = true;
    },
    hideModal() {
      this.modalActive = false;
    },
  },
};
</script>

<style>
body {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  display: flex;
  font-family: Inter, sans-serif;
  background: #E5E5E5;
}

.control_btns {
  width: 174px;
  height: 42px;
  display: flex;
  justify-content: space-between;
  margin: 24px 30px 0 0;
}

.control_btns button {
  width: 42px;
  height: 100%;
  border-radius: 10px;
  background: #FFFFFF;
  box-shadow: 0 4px 15px rgba(234, 235, 237, 0.5);
  border: none;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  color: #A3B2C0;
}

.control_btns_wrapper {
  width: 100%;
  display: flex;
  justify-content: flex-end;
}

.board_cards_row {
  width: calc(100% - 30px);
  display: flex;
  margin: 22px -15px 0 15px;
  padding-right: 15px;

}

.content {
  width: 100%;
  height: 100%;
}

.board_card_wrapper {
  width: 25%;
  flex: 25%;
  margin: 0 15px;
}
</style>
