<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

const menuSwitch = ref(false)

function toggleMenu() {
  menuSwitch.value == true ? (menuSwitch.value = false) : (menuSwitch.value = true)
}
</script>

<template>
  <div :class="menuSwitch == true ? 'menuOn' : 'menuOff'">
    </div>
    <div @click="menuSwitch = false" :class="menuSwitch == true ? 'screenMenuOn' : 'screenMenuOff'"></div>

  <header>
      <nav>
        <div>
          <i class="bi bi-list" @click="toggleMenu()"></i>
        </div>
      <div ><img class="logo" src="../src/imgs/HBO_Max_Logo.svg.png" alt=""></div>
      <div><i class="bi bi-search"></i></div>
      </nav>

  </header>
  

</template>

<style scoped>
.screenMenuOff {
  visibility: hidden;
  z-index: 1;
  top: 0;
  left: 0;
  position: absolute;
  height: 100vh;
  width: 100vw;
  transition: 0.4s ease-in-out;
}
.screenMenuOn {
  z-index: 1;
  top: 0;
  left: 0;
  position: absolute;
  height: 100vh;
  width: 100vw;
  background-color: rgba(0, 0, 0, 0.596);
  transition: 0.4s ease-in-out;
}
.menuOff {
  z-index: 2;
  left: -500px;
  position: absolute;
  transition:0.3s ease-in-out;
  height: 100%;
  width: 330px;
  background-color: rgb(32, 32, 32);

}
.menuOn {
  z-index: 2;
  position: absolute;
  height: 100%;
  width:330px;
  background-color: rgb(32, 32, 32);
  transition: 0.5s;
  left: 0%;
  box-shadow: 6px 0px 100px rgba(0, 0, 0, 0.384);
}
header{
  width: 100vw;
  height: 80px;
  background-color: rgb(32, 32, 32);
  opacity: 0.98;
  display: flex;
  align-items: center;
  justify-content: center
}
nav{
  width: 1800px;
  height: 25px;
  display: flex;
  justify-content: space-around;
    align-items: center;

}
.logo{
  width: 120px;
}
.bi{
  font-size: 2em;
color: white;
}
</style>
