<template>
  <div id="main">
    <ParentOne @openPopup="openPopupParent1($event)"></ParentOne>
    <ParentTwo @openPopup="openPopupParent2($event)"></ParentTwo>
    <PopupOne ref="popup1" :msg="msg"></PopupOne>
    <PopupTwo ref="popup2" :msg="msg"></PopupTwo>
    <PopupThree ref="popup3" :msg="msg"></PopupThree>
  </div>
</template>

<script>
import ParentOne from './components/ParentOne';
import ParentTwo from './components/ParentTwo';
import PopupOne from './components/PopupOne';
import PopupTwo from './components/PopupTwo';
import PopupThree from './components/PopupThree';
import { ref } from 'vue'
export default {
  name: "App",
  setup() {
    let msg = ref('');
    const popup1 = ref(null);
    const popup2 = ref(null);
    const popup3 = ref(null);
    const openPopupParent1 = (e) => {
      msg.value = e.text
      switch (e.value) {
        case 1:
          popup1.value?.open()
          break;
        case 2:
          popup2.value?.open()
          break;
        case 3:
          popup3.value?.open()
          break;
        default:
          break;
      }
    };
    const openPopupParent2 = (e) => {
      msg.value = e.text
      switch (e.value) {
        case 1:
          popup1.value?.open()
          break;
        case 2:
          popup2.value?.open()
          break;
        case 3:
          popup3.value?.open()
          break;
        default:
          break;
      }
    };
    return {
      openPopupParent1,
      openPopupParent2,
      popup1,
      popup2,
      popup3,
      msg,
    }
  },
  components: {
    ParentOne,
    ParentTwo,
    PopupOne,
    PopupTwo,
    PopupThree
  },
};
</script>

<style>
#main{
  background: #F8F8F8;
  display: flex;
  justify-content: center;
  height: 100vh;
}
.button{
  height: 30px;
  display: block;
  text-align: center;
  cursor: pointer;
  border: 1px solid #CCC;
}
.button:hover{
  background: #333;
  color: #FFF;
}
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
    opacity: 0;
}
.background{
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 0.5rem;
  display: flex;
  align-items: center;
  z-index: 9998;
}
.popup {
  position: fixed;
  top: 50%;
  transform: translate(0, -50%);
  padding: 0.5rem;
  display: flex;
  align-items: center;
  z-index: 9999;
}
.box-popup{
  background: #fff;
  border-radius: 10px;
  box-shadow: 2px 4px 8px rgba(0, 0, 0, 0.2);
  width: 500px;
  height: 300px;
  margin-left: auto;
  margin-right: auto;
  padding: 15px;
}
h3{
  font-family: Arial, Helvetica, sans-serif;
  font-size: 30px;
}
p{
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
}
.parent{
  background: #FFFFFF;
  border: 1px solid #CCC;
  width: 500px;
  height: 300px;
  border-radius: 10px;
  display: grid;
  grid-template-columns: repeat(3,1fr);
  grid-gap: 15px;
  align-items: center;
  padding: 15px;
  margin: 30px 15px;
}
.parent h3{
  grid-area: 1 /span 3;
}
</style>
