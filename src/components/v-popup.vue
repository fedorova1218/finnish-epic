<template>

    <div class="wrap" @click.self="closePopup">
        <div class="v-popup-close">
             <button @click="closePopup"> <img src="@/assets/icons/close.svg" ></button>
        </div>   
            <transition name="scale">
                <div class='v-popup'>

                    <div class="v-popup-img">
                        <slot></slot>
                    </div>
                </div>
            </transition>
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

    padding: 20px;
}

.v-popup {

    width: 100%;
    max-width: 800px;
    overflow: hidden auto;
    box-shadow: 0 0 17px 0 #252424;
    border-radius: 40px;
}

.v-popup-close{
    position: absolute;
    top: 10px;
    right: 30px;
    
    
    // &_img{
    //     display:flex;
    //     justify-content: center;
    //     align-items: center;
       
    // }
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

.scale-enter-active,
.scale-leave-active {
  transition: all 7s ease-in-out;
}

.scale-enter,
.scale-leave-to {
    transform: scale(.3);
}


</style>
