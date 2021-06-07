<template>
<div class = car>
  
      <button @click="prevSlide" class="fe-button"> <img src = "@/assets/icons/left.svg"></button>
  <div class="wrapper_container">
    <div class = "wrapper">
      <div class ='v-carusel' :style = "{'margin-left': '-' + (310 * currentSlideIndex) + 'px' }">
        <v-carusel-item
          v-for="item in carusel_data"
          :key="item.id"
          :item_data = "item"
        />
      </div>
        
    </div>
  </div>
  <button @click="nextSlide" class="fe-button"> <img src = "@/assets/icons/right.svg" ></button>
</div>
</template>

<script>
import vCaruselItem from './v-carusel-item'

export default{
  name: 'v-carusel',
  components: {
    vCaruselItem
  },
  props: {
    carusel_data: {
      type: Array,
      default: ()=> []
    }
  },
  data() {
    return {
      currentSlideIndex: 0
    }
  },
  methods: {
    prevSlide (){
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--
      } 
    },
    nextSlide (){
      if (this.currentSlideIndex >= this.carusel_data.length - 1) {
        this.currentSlideIndex=0;
        
    } else {
      this.currentSlideIndex++
      }
    }
  }
}
</script>


<style lang = "scss">

.car {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
button{
  
  z-index: 2;
  width: 50px;
  height: 50px;
  background: transparent;
  outline: none;
  border: none;
}

button img {
  top: 3vh;
  right: 3vh;
  width: 70px;
  height: 70px;
}
.wrapper_container {
  
  display: flex;
  flex-direction: row;
  
  margin: 5vh;
  height: auto;
  width: auto;
  
}

.wrapper {
  max-width: 320px;
  overflow: hidden;

}


.v-carusel {
  display: flex;
  transition: all ease .10s;
}
</style>