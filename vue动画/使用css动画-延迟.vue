<template>
  <div class="welcome">
    <img src="../../public/img/xh.png" alt="" class="snow move-ani"   key="snow" >
    <img src="../../public/img/dl.png" alt="" class="lantern fade-ani"  key="lantern">
    <img src="../../public/img/chun.png" alt="" class="text-chun rotate-ani"  key="text-chun">
    <img src="../../public/img/qq.png" alt="" class="btn-qq scale-ani"  key="btn">
    <img src="../../public/img/xc.png" alt="" class="text fade-ani-2"  key="text">
  </div>
</template>

<script>
export default {
  data () {
    return {
     
    }
  },
  created() {
   
  },
  methods: {
   
  }
}
</script>

<style lang="less">
 .move-ani {
  animation: move-in 1s .1s ease both ;
}
.fade-ani {
  animation: fadeIn 1.5s .8s ease both;
} 
.fade-ani-2 {
  animation: fadeIn 1s 1.5s ease both;
} 
.rotate-ani{
  animation: rotateIn 1s 1s ease both;
}
.scale-ani {
  animation: scaleIn 1s 1.5s ease both;
}
@keyframes scaleIn {
  0% {
    opacity: 0;
    left: 50%;
    transform-origin: 50% 50%;
    transform: translateX(-50%) scale(0.5);
  }
  100% {
    opacity: 1;
    left: 50%;
    transform-origin: 50% 50%;
    transform: translateX(-50%) scale(1)
  }
}
@keyframes rotateIn {
  0% {
    opacity: 0;
    left: 50%;
    top: 44%;
    transform-origin: 50% 60%;
    transform: translate(-50%,-50%) rotate(-180deg);
  }
  1% {
    opacity: 1;
  }
  100% {
    opacity: 1;
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
