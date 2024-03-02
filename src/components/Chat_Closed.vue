<template>
  <div className="chat-closed">
    <button class="chat-button" @click="changeChatFlag(2)">
      <svg viewBox="0 0 8 14" class="svg-open svg">
        <use href="../svg/Closed.svg#closed" />
      </svg>
    </button>
    <button class="chat-button">
      <svg viewBox="0 0 21 22" class="svg-home svg">
        <use href="../svg/Subtract.svg#home" />
      </svg>
    </button>
    <button class="chat-button">
      <svg viewBox="0 0 22 22" class="svg-cursor svg">
        <use href="../svg/Cursor.svg#cursor" />
      </svg>
    </button>
    <button class="chat-button">
      <svg viewBox="0 0 21 22" class="svg-chat svg">
        <use href="../svg/Chat.svg#chat" />
      </svg>
    </button>
  </div>
  </template>
  
  
  <script>
  export default {
    props: {
    changeChatFlag: {
      type: Function,
      required: true
    },
    chatFlag: {
      type: Number,
      required: true
    }
  }
  }
  </script>
  
  <style scoped>
.chat-closed {
  height: 100vh;
  width: 56px;
  border-left: 1px solid #E5E5E6;
  display: flex;
  flex-direction: column;
  gap: 8px;
  border-top-right-radius: 15px;
  border-bottom-right-radius: 15px;
  padding: 8px;
}

.chat-button {
  border: #F2F2F2;
  border-radius: 8px;
  height: 40px;
  width: 40px;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.svg-open {
  width: 8px;
  height: 14px;
}

.svg-home {
  width: 21px;
  height: 22px;
  fill: #8A898E;
}

.svg-cursor {
  width: 22px;
  height: 22px;
}

.svg-chat {
  width: 21px;
  height: 22px;
}
  </style>