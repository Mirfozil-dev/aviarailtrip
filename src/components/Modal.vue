<template>
  <div :class="active ? 'active' : ''" class="modal_bg">
    <div class="modal">
      <div class="modal_body">
        <h6>Новая доска</h6>
        <label for="title">
          Название
        </label>
        <input id="title" type="text" placeholder="Sunrise Tour Inc">
        <label for="section">
          Раздел
        </label>
        <div id="section" class="section_select">
          Placeholder
          <i class="ri-arrow-down-s-line"></i>
        </div>
      </div>
      <div class="modal_footer">
        <button class="add">Создать</button>
        <button class="close" @click="hideModal">Отмена</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: {
    active: Boolean,
  },
  methods: {
    hideModal() {
      this.$emit('hidemodal');
    },
  },
};
</script>

<style scoped>
.modal_bg {
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.50);
  position: absolute;
  z-index: -1;
  opacity: 0;
  transition: .3s;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal_bg.active {
  z-index: 1;
  opacity: 1;
}

.modal {
  width: 383px;
  height: 393px;
  background: #FFFFFF;
  border-radius: 16px;
  margin-left: 269px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 26px;
}

.modal h6 {
  margin: 0 0 6px 0;
  font-weight: 600;
  font-size: 18px;
  color: #283E54;
}

.modal label {
  font-weight: normal;
  font-size: 12px;
  color: #283E54;
  margin-top: 18px;
}

.modal button {
  height: 46px;
  border-radius: 10px;
  cursor: pointer;
}

.modal button.add {
  background: #FF6F20;
  color: #FFFFFF;
  border: none;
  margin-bottom: 12px;
}

.modal button.close {
  border: 1px solid #FF6F20;
  color: #FF6F20;
  background: none;
}

.modal input, .modal .section_select {
  height: 46px;
  border-radius: 10px;
  border: 1px solid #DBE3E9;
  padding: 0 14px;
  margin-top: 10px;
  outline: none;
  font-size: 14px;
  display: flex;
  align-items: center;
}

.modal input::placeholder {
  color: #AAB2B9;
}

.modal .section_select {
  justify-content: space-between;
  color: #AAB2B9;
}

.modal .section_select i {
  color: #647C94;
  font-size: 20px;

}

.modal_body, .modal_footer {
  width: 100%;
  display: flex;
  flex-direction: column;
}
</style>