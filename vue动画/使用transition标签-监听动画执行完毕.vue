<template>
  <div class="welcome">
    <!-- <div class="lantern"></div>
    <div class="text-chun"></div> -->
    <!-- <transition name="snow"  :duration="{ enter: 100, leave: 2800 }" key="snow"> -->
    <transition name="move"  key="snow" >
      <img src="../../public/img/xh.png" alt="" class="snow" v-if="showSnow"   >
    </transition>

    <transition name="fade"  key="lantern">
      <img src="../../public/img/dl.png" alt="" class="lantern"  v-if="showLantern" @animationend="moveEnd" @transitiond="moveEnd">
    </transition>
    <transition name="rotate"  key="text-chun">
      <img src="../../public/img/chun.png" alt="" class="text-chun"  v-if="showChun" @animationend="roateEnd">
    </transition>
    <transition name="scale"  key="btn">
      <img src="../../public/img/qq.png" alt="" class="btn-qq"  v-if="showBtn"  @click="btnClick">
    </transition>
    <transition name="fade"  key="text">
      <img src="../../public/img/xc.png" alt="" class="text"  v-if="showText">
    </transition>
  </div>
</template>

<script>

// bug: animateionend时间有时候没有监听到，导致后面动画没有执行

export default {
  data () {
    return {
      showLantern:false,
      showSnow:false,
      showChun:false,
      showBtn:false,
      showText:false
    }
  },
  created() {
    setTimeout(()=>{
      this.showSnow = true
    },100)
    setTimeout(()=>{
      this.showLantern = true
    },500)
  },
  methods: {
    moveEnd() {
      console.log('end')
      this.showChun = true
    },
    roateEnd() {
      console.log('rotate')
      this.showBtn=true
      this.showText = true
    },
    btnClick() {
      alert('click')
    }
  }
}
</script>

<style lang="less">
 .move-enter-active {
  animation: move-in 1s ease;
}
.fade-enter-active {
  animation: fadeIn 1s ease;
} 
.rotate-enter-active {
  animation: rotateIn .5s ease;
}
.scale-enter-active {
  animation: scaleIn .5s ease;
}
@keyframes scaleIn {
  0% {
    left: 50%;
    transform-origin: 50% 50%;
    transform: translateX(-50%) scale(0.5);
  }
  100% {
    left: 50%;
    transform-origin: 50% 50%;
    transform: translateX(-50%) scale(1)
  }
}
@keyframes rotateIn {
  0% {
    left: 50%;
    top: 44%;
    transform-origin: 50% 80%;
    transform: translate(-50%,-50%) rotate(-180deg);
  }
  100% {
    left: 50%;
    top: 44%;
    transform-origin: 50% 80%;
    transform: translate(-50%,-50%) rotate(0deg);
  }
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes move-in {
  0% {
     width: 95%;
    top: -50%;
    left: 50%;
    transform: translate(-50%,-50%)

  }
 
  100% {
    width: 95%;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
  }
}

  .welcome {
    width: 100%;
    height: 100%;
    background-image: url(../../public/img/bg.png);
    background-size: cover;
    background-repeat: no-repeat;
    position: relative;
    .snow {
      position: absolute;
      width: 95%;
      left: 50%;
      top: 50%;
      transform: translate(-50%,-50%);
    }
    .lantern {
      position: absolute;
      width: 80%;
      left: 50%;
      top: 50%;
      transform: translate(-50%,-50%);
    }
    .text-chun {
      position: absolute;
      height:  220px;
      left: 50%;
      top: 44%;
      transform: translate(-50%,-50%);
      z-index: 50;
    }
    .text {
      position: absolute;
      height: 60px;
      left: 50%;
      top: 3%;
      transform: translateX(-50%);
    }
    .btn-qq {
      position: absolute;
      width: 110px;
      left: 50%;
      bottom: 10%;
      transform: translateX(-50%);
      z-index: 100;
    }
  }



</style>
