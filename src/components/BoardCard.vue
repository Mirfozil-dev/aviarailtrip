<template>
  <div class="board_card">
    <div>
      <h6>
        {{ card.title }}
      </h6>
      <p>
        Раздел:
        <span>
        {{ card.section }}
      </span>
      </p>
      <p>
        Дата создания:
        <span>
        {{ card.date }}
      </span>
      </p>
    </div>
    <button>
      Открыть
    </button>
  </div>
</template>

<script>
export default {
  name: 'BoardCard',
  props: {
    card: Object,
  },
};
</script>

<style scoped>
.board_card {
  height: 187px;
  border-radius: 16px;
  background: #FFFFFF;
  box-shadow: 0 4px 15px rgba(224, 227, 232, 0.5);
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.board_card h6 {
  font-weight: 500;
  font-size: 16px;
  margin: 0 0 18px 0;
}

.board_card p {
  color: #A3B2C0;
  font-size: 14px;
  margin: 0 0 10px 0;
}

.board_card p span {
  color: #283E54;
}

.board_card button {
  height: 46px;
  background: none;
  border: 1px solid #FF6F20;
  color: #FF6F20;
  font-size: 14px;
  font-weight: 600;
  border-radius: 10px;
}
</style>