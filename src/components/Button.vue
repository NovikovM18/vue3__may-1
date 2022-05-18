<template>
  <transition appear name='but'>
    <a 
      href="tel: +380674016977"
      id="box" 
      class="box"
      @mousemove="onMousemove"
    >
      <div
          class="button"
          id="button"
        >
        <p 
          class="button__description" 
          id="text"
        >Заказать уборку</p>
      </div>
    </a>  
  </transition>
</template>
<script>
export default {
    data() {
    return {
      showButton: 0
    }
  },
  mounted() {
    window.addEventListener("scroll", function() {
      const box = document.getElementById('box');
      const button = document.getElementById('button');
      const text = document.getElementById('text');
      const down = document.documentElement.offsetHeight - window.visualViewport.height;
      if (document.documentElement.clientWidth <= 768) {
        if (window.scrollY + 99 >= down) {
          button.style.opacity = 0;
          text.style.opacity = 0;
          box.style.zIndex = 0;
        } else {
          button.style.opacity = 1;
          text.style.opacity = 1;
          box.style.zIndex = 1;
        }
        return;
      }
      if (window.scrollY < 100) {
        button.style.width = 196 + 'px';
        button.style.height = 196 + 'px';
        box.style.width = 300 + 'px';
        box.style.height = 300 + 'px';
        text.style.fontSize = 18 + 'px';
      } else if (window.scrollY >= 100 && window.scrollY + 99 < down) {
        button.style.width = 144 + 'px';
        button.style.height = 144 + 'px';
        box.style.width = 246 + 'px';
        box.style.height = 246 + 'px';
        text.style.fontSize = 14 + 'px';
        button.style.opacity = 1;
        text.style.opacity = 1;
        box.style.zIndex = 5;
      } else if (window.scrollY + 99 >= down) {
        button.style.opacity = 0;
        text.style.opacity = 0;
        box.style.zIndex = 0;
      } 
    });
  },
  methods: {
    onMousemove(e) {
      const box = document.getElementById('box');
      const button = document.getElementById('button');
      const text = document.getElementById('text');
      const cenX = box.offsetLeft + box.offsetWidth/2; 
      const cenY = box.offsetTop + box.offsetHeight/2;
      if (e.target.closest('#box')) {
        if (button.offsetWidth >= 196) {
          button.style.left = (e.clientX - cenX + box.offsetWidth/2)/3 + 'px';
          button.style.top = (e.clientY - cenY + box.offsetHeight/2)/3 + 'px';
          text.style.left = (e.clientX - cenX + box.offsetWidth/2)/5 + 'px';
          text.style.top = (e.clientY - cenY + box.offsetHeight/2)/2 + 'px';
        } else if (button.offsetWidth < 196) {
          button.style.left = (e.clientX - cenX + box.offsetWidth/2)/3 + 'px';
          button.style.top = (e.clientY - cenY + box.offsetHeight/2)/3 + 'px';
          text.style.left = (e.clientX - cenX + box.offsetWidth/2)/7 + 'px';
          text.style.top = (e.clientY - cenY + box.offsetHeight/2)/2 + 'px';
        }
      }
      window.addEventListener('mousemove', e => {
        if (!e.target.closest('#box')) {
        button.style.left = (box.offsetWidth - button.offsetWidth) / 2 + 'px';
        button.style.top = (box.offsetHeight - button.offsetHeight) / 2 + 'px';
        text.style.left = 'auto';
        text.style.top = 'auto';
      }
      })
    }
  }
}
</script>
<style lang='scss'>
  .box {
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 5;
    position: fixed;
    bottom: 0;
    width: 300px;
    height: 300px;
    transition: 1s;
      @media (max-width: 768px) {
        width: 124px;
        height: 124px;
      }
  }
  .button {
    overflow: hidden;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 196px;
    height: 196px;
    border-radius: 50%;
    background: #5A30F0;
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: transform 500ms ease;
    &:hover {
      cursor: pointer;
    }
    &__description {
      margin: 0;
      padding: 0;
      position: absolute;
      width: 130px;
      font-size: 18px;
      line-height: 130%;
      display: flex;
      align-items: center;
      text-align: center;
      letter-spacing: 0.03em;
      text-transform: uppercase;
      color: #FFFFFF;
      transform: rotate(-15deg);
      transition: 1s;
      transition: transform 500ms ease;
        @media (max-width: 768px) {
          width: 98px;
          font-size: 12px;
          width: 112px;
          height: 112px;
        }
    }
      @media (max-width: 768px) {
        width: 112px;
        height: 112px;
      }
  }

.but-enter-active,
.but-leave-active {
  opacity: 1;
  transition: opacity 1s ease;
}

.but-enter-from,
.but-leave-to {
  opacity: 0;
}
</style>
