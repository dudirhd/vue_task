<template>
 <nav className="navbar">
    <button className="button__change-theame">
      <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="none">
        <path fill="#fff" fill-rule="evenodd" d="M24 0C10.745 0 0 10.745 0 24s10.745 24 24 24V0Z" clip-rule="evenodd"/>
        <path fill="#0E1420" fill-rule="evenodd" d="M24 48c13.255 0 24-10.745 24-24S37.255 0 24 0v48ZM24 16.459a7.698 7.698 0 0 0-2.934.552l-.027.01a7.595 7.595 0 0 0-4.068 9.959A7.59 7.59 0 0 0 24 31.645V29.19a5.173 5.173 0 0 1-4.727-3.176c-1.102-2.623.114-5.652 2.736-6.754a5.095 5.095 0 0 1 1.991-.4v-2.4Zm-3.697-1.264c.473-.217.736-.745.629-1.277l-.113-.268-1.55-3.694c-.172-.558-.825-.913-1.383-.742a.202.202 0 0 1-.06.083c-.014.011-.024.015-.024.015-.536.225-.815.91-.537 1.422l.023.054 1.55 3.694c.172.558.749.882 1.33.765a1.12 1.12 0 0 0 .135-.052ZM9.983 28.78c-.558.172-.883.749-.765 1.33.171.557.748.881 1.329.764l.267-.112 3.694-1.551c.557-.172.882-.749.764-1.329-.171-.558-.748-.882-1.329-.765l-.267.113-3.694 1.55Zm.731-11.454a1.191 1.191 0 0 0-.9 2.205l3.724 1.522a1.191 1.191 0 0 0 .9-2.204l-3.724-1.523Zm9.637 15.603a1.191 1.191 0 0 0-1.553.652l-1.521 3.724a1.192 1.192 0 0 0 2.204.901l1.521-3.724a1.192 1.192 0 0 0-.651-1.553Z" clip-rule="evenodd"/>
        <path fill="#fff" fill-rule="evenodd" d="M24 31.645a7.603 7.603 0 0 0 2.928-.596l.027-.011c3.836-1.628 5.656-6.101 4.04-9.947A7.71 7.71 0 0 0 24 16.46v2.4a5.173 5.173 0 0 1 4.747 3.176c1.102 2.623-.113 5.653-2.736 6.754a5.093 5.093 0 0 1-2.011.4v2.456Zm6.194 7.107c.473-.217.736-.746.629-1.277l-.113-.268-1.55-3.694c-.172-.558-.825-.913-1.383-.742a.2.2 0 0 1-.06.082.116.116 0 0 1-.024.016c-.536.225-.815.91-.537 1.422l.023.054 1.55 3.694c.172.558.749.882 1.33.764.046-.014.091-.031.135-.051ZM32.77 20.22c-.118-.58.206-1.157.764-1.329l3.694-1.55.267-.113c.58-.118 1.158.207 1.329.765.118.58-.207 1.157-.765 1.328l-3.693 1.551-.268.113c-.58.117-1.157-.207-1.328-.765ZM28.432 9.887c.249-.608.945-.9 1.553-.652.684.28.976.976.652 1.553l-1.522 3.724a1.191 1.191 0 0 1-2.204-.9l1.521-3.725Zm4.444 17.783c.249-.608.945-.9 1.553-.652l3.724 1.522a1.192 1.192 0 0 1-.9 2.204l-3.725-1.522a1.192 1.192 0 0 1-.652-1.552Z" clip-rule="evenodd"/>
      </svg>
    </button>
    <button class="event" @click="changeNavFlag(1)" :class="navFlag == 1 ? 'active'  : ''">
      <svg viewBox="0 0 24 24" class="svg">
        <use href="../svg/Subtract.svg#home"/>
      </svg>
    </button>
    <button class="event" @click="changeNavFlag(2)" :class="navFlag == 2 ? 'active'  : ''">
      <svg viewBox="0 0 24 24" class="svg">
        <use href="../svg/Union1.svg#union1"/>
      </svg>
    </button>
    <button class="event" @click="changeNavFlag(3)" :class="navFlag == 3 ? 'active'  : ''">
      <svg viewBox="0 0 24 24" class="svg">
        <use href="../svg/Union2.svg#union2"/>
      </svg>
    </button>
    <button className="button__avatar"></button>
 </nav>
</template>


<script>
export default {
  props: {
    changeNavFlag: {
      type: Function,
      required: true
    },
    navFlag: {
      type: Number,
      required: true
    }
  }
}
</script>

<style scoped>
button {
  background: transparent;
  cursor: pointer;
  border: 0;
}

.navbar {
  width: 80px;
  height: 100vh;
  border-right: 1px solid #E5E5E6;
  padding-top: 16px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.event::before {
  content: '';
  position: absolute;
  height: 100%;
  width: 4px;
  border-top-right-radius: 4px;
  border-bottom-right-radius: 4px;
  scale: 0;
  left:0;
  transition: scale 0.5s ease; 
  background: #006CFF;
}

.event:hover::before {
  scale: 1;
} 

.event {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
}

.event:hover{
  .svg {
    fill: #006CFF;
    transition: 0.5s;
  }

  .event::before {
    scale: 1;
    transition: scale 0.5s ease; 
  }
}

.active {
  .svg {
    fill: #006CFF;
  }

  .event::before {
    scale: 1;
  }
}

.svg {
  height: 24px;
  width: 24px;
  fill: #8A898E;
}

.button__avatar {
  background-image: url("../pictures/Avatars.png");
  width: 48px;
  height: 48px;
  align-self: center;
  margin-top: auto;
  margin-bottom: 16px;
  border-radius: 50%;
}
</style>