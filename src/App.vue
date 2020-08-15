<template>
  <div id="app">
<button class="button" @click="showModal = true">
Show Modal
</button>
<transition name="fade" appear>
  <div class="modal-overlay" v-if="showModal"
  @click="showModal = false">

  </div>
</transition>
<transition name="slide"><div class="modal" v-if="showModal"><h1>Lorem</h1><p>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
<button class="button" @click="showModal = false">Close Modal</button>
</div></transition>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      showModal:true
    }
  }


}
</script>

<style>
body{margin:0;
padding:0;
box-sizing: border-box;
font-family: 'montserrat',sans-serif;
}

#app{
display: flex;
  position:relative;
  justify-content: center;
  align-items: center;
  width: 100vw;
  min-height: 100vh;
  overflow-x: hidden;
  border: 1px solid black;
}
.button{
  appearance:none;
  outline: none;
  border:none;
  background: none;
  cursor:pointer;

  display: inline-block;
  padding: 15px 25px;
  background-image: linear-gradient(to right,#CC2E5D,#FF5858);
  border-radius: 8px;

  color:#FFF;
  font-size: 18px;
  font-weight: 700;

  box-shadow: 3px 3px rgba(0, 0, 0, 0.4);
  transition: 0.4s ease-out;
}
.button:hover{
  box-shadow: 6px 6px rgba(0, 0, 0, 0.6);
}

.modal-overlay{
  position: absolute;
  top:0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 98;
  background-color: rgba(0, 0, 0, 0.3);
}
.modal{
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 99;

  width: 100%;
  max-width: 400px;
  background-color: #fff;
  border-radius: 16px;


padding: 25px;
}

.fade-enter-active,
.fade-leave-active{
  transition: opacity .5s;
}
.fade-enter-active,
.fade-leave-to{
  opacity: 0;
}



.slide-enter-active,
.slide-leave-active{
  transition: transform .5s;
}
.slide-enter,
.slide-leave-to{
  transform:translateY(-50%) translateX(100vw);
}
h1{
  color: #222;
  font-size: 32px;
  font-weight: 900;
  margin-bottom: 15px;
}
p{
  color: #666;
  font-size: 20px;
  font-weight: 400;
  margin-bottom: 15px;
}

</style>
