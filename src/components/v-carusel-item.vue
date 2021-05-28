<template>
  <div class="v-carusel-item">
    <transition name="pop">
      <v-popup v-if="isInfoPopVisible" @closePopup="closeInfoPopup">
        <img
          class="card-info"
          :src="require('../assets/' + item_data.img_info)"
          alt=""
        />
      </v-popup>
    </transition>

    <img
      class="card v-show-info fe-button"
      :src="require('../assets/' + item_data.img)"
      alt=""
      @click="showPopupInfo"
    />
  </div>
</template>

<script>
import vPopup from "../components/v-popup";
export default {
  name: "v-carusel-item",
  components: {
    vPopup,
  },
  props: {
    item_data: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      isInfoPopVisible: false,
    };
  },

  computed: {},
  methods: {
    showPopupInfo() {
      this.isInfoPopVisible = true;
    },
    closeInfoPopup() {
      this.isInfoPopVisible = false;
    },
  },
};
</script>

<style lang="scss">
.card {
  width: 260px;
  height: 446px;
  filter: drop-shadow(8px 8px 15px rgba(0, 0, 0, 0.25));
  border-radius: 20px;
  margin: 5vh;
  transition: all 0.4s;
  animation-timing-function: ease-in-out;
}
.card-info {
  background-size: cover;
  scroll-behavior: smooth;
  object-fit: cover;
  width: 800px;
  height: 1700px;
}
.card:hover {
  -webkit-transform: translateX(-10px);
  transform: translateY(-10px);
}

.pop-enter-active,
.pop-leave-active {
  transition: all 0.7s ease-in-out;
}

.pop-enter,
.pop-leave-to {
  opacity: 0;
}
</style>