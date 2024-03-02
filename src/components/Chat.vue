<template>
<div className="chat">
  <div className="chat__top">
    <button className="button__close-chat" @click="changeChatFlag(1)">
      <svg viewBox="0 0 7.78 14" class="svg-close">
        <use href="../svg/Opened.svg#opened"/>
      </svg>
    </button>
    <button className="button__people">
      <svg viewBox="0 0 10.07 14" class="svg-people">
        <use href="../svg/Guy.svg#guy"/>
      </svg>
      <p className="button__people-count">1428</p>
    </button>
  </div>
  <div className="chat__button-container">
    <button className="chat__button">Global</button>
    <button className="chat__button">DM</button>
    <button className="chat__button">Q&A</button>
  </div>
  <div className="chat__no-messages">
    <div className="chat__no-messages-container">
      <svg viewBox="0 0 103.75 99.75" class="svg-no-messages">
        <use href="../svg/No_questions.svg#no_questions"/>
      </svg>
      <h3 className="no_questions-title">No question yet</h3>
      <p className="no_questions-subtitle">Send a question for the speakers</p>
    </div>
  </div>
  <div className="chat__message-zone">
    <div className="chat__input-container">
      <input type="text" placeholder="Say something" className="chat__input">
      <button className="emoji">
        <svg viewBox="0 0 10 18" class="svg-lightning">
          <use href="../svg/Lightning.svg#lightning"/>
        </svg>
      </button>
      <button className="emoji">
        <svg viewBox="0 0 20 20" class="svg-smile">
          <use href="../svg/Smile.svg#smile"/>
        </svg>
      </button>
    </div>
    <button className="button-send">
      <svg viewBox="0 0 16 14" class="svg-arrow">
          <use href="../svg/Arrow.svg#arrow"/>
      </svg>
      280
    </button>
  </div>
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
  .chat {
    height: 100vh;
    width: 320px;
    border-left: 1px solid #E5E5E6;
    display: flex;
    flex-direction: column;
    border-top-right-radius: 15px;
    border-bottom-right-radius: 15px;
  }

  .chat__top {
    padding: 8px;
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid #E5E5E6;
  }

  .button__close-chat {
    background: #F2F2F2;
    border: 0;
    width: 40px;
    height: 40px;
    border-radius: 8px;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

.svg-close {
  height: 14px;
  width: 8px;
}

.button__people {
  background: #F2F2F2;
  border: 0;
  border-radius: 8px;
  width: 62px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 7px;
}

.svg-people {
  width: 10px;
  height: 14px;
}

.button__people-count {
  font-size: 11px;
  line-height: 13px;
  color: #006CFF;
}

.chat__button-container {
  width: 100%;
  border-bottom: 1px solid #E5E5E6;
}

.chat__button {
  position: relative;
  border: 0;
  background: transparent;
  width: 33.3%;
  height: 56px;
}

.chat__button::before {
  content: '';
  position: absolute;
  width: 97%;
  height: 4px;
  border-bottom-right-radius: 4px;
  border-bottom-left-radius: 4px;
  scale: 0;
  top: 0;
  left: 3px;
  transition: scale 0.5s ease; 
  background: #006CFF;
}

.chat__button:hover::before {
  scale: 1;
}

.chat__button:hover {
    .chat__button::before {
    scale: 1;
    transition: scale 0.5s ease; 
  }
}

.chat__no-messages {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.chat__no-messages-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.svg-no-messages {
  width: 100px;
  height: 104px;
  padding: 20.5px 17px 15.5px 15px;
}

.no_questions-title {
  font-weight: 600;
  font-size: 18px;
  line-height: 22px;
}

.no_questions-subtitle {
  color: #8A898E;
}

.chat__message-zone {
  height: 56px;
  border-top: 1px solid #E5E5E6;
  display: flex;
  flex-direction: row;
  padding: 8px;
  gap: 8px;
}

.chat__input-container {
  width: 256px;
  display: flex;
  align-items: center;
  gap: 8px;
  border: 1px solid #E5E5E6;
  border-radius: 8px;
  padding: 0 8px 0 8px;
}

.chat__input {
  height: 18px;
  border: 0;
  background: transparent;
}

.chat__input:focus-visible {
  outline: 0;
}

.emoji {
  background: transparent;
  border: 0;
  padding: 0;
  display: flex;
  width: 24px;
  height: 24px;
  align-items: center;
  justify-content: center;
}

.svg-lightning {
  width: 10px;
  height: 18px;
}

.svg-smile {
  width: 20px;
  height: 20px;
}

.button-send {
  border: 0;
  padding: 0;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  background: #F2F2F2;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4px;
  font-size: 11px;
  line-height: 13px;
  color: #8A898E;
}

.svg-arrow {
  width: 16px;
  height: 16px;
}
</style>