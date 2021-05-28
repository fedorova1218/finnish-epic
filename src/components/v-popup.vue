<template>

    <div class = "wrap">
        <div class = "v-popup-close">
             <button @click="closePopup"> <img src = "@/assets/icons/close.svg" ></button>
            </div>   
        <div class = 'v-popup'>
            <div class = "v-popup-img">
                <slot></slot>
            </div>
        </div>
    </div> 

</template>

<script>
export default{
    name: "v-popup",
    props: {},
    data() {
        return{}
    },
    methods: {
        closePopup() {
            this.$emit( 'closePopup')
        }
    }
}
</script>

<style lang="scss">

.wrap {
    background: rgba(24, 24, 24, 0.7);
    display:flex;
    justify-content: center;
   
    position: fixed;
    right: 0;
    left: 0;
    top: 0;
    bottom: 0;
    z-index: 5;
    
}
.v-popup {
    
    position: fixed;
    max-width: 800px;
    max-height: 550px;
    top: 20px;
    z-index: 5;
    overflow: hidden auto;
   width: 100%;
   height: 100%;
   
    box-shadow: 0 0 17px 0 #252424;
.v-popup_close{
        display: flex;
        justify-content: end;
        align-items: end;
        text-align: end  !important;
        top: 3vh;
        right: 3vh;
    }
    &_img{
        display:flex;
        justify-content: center;
        align-items: center;
       
    }
}
.v-popup::-webkit-scrollbar {
  width: 8px;               /* ширина scrollbar */
}
.v-popup::-webkit-scrollbar-track {
  background: var( --gold-dark);        /* цвет дорожки */
}
.v-popup::-webkit-scrollbar-thumb {
  background-color: var( --primary-color);    /* цвет плашки */
  border-radius: 20px;       /* закругления плашки */
  border: 3px solid var( --gold-dark);  /* padding вокруг плашки */
}

</style>
