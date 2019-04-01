<template>
  <div class="main">
    <div class="head">
      <div class="dk-green-bkg h50 right-left-p5">
          <button class="menu-button material-icons" v-on:click="closeMenuBar">menu</button>
          <p class="fit centered twenty white-text roboto relative top-padding-10">Production</p>
      </div>
      <div class="tab-container dk-gray h60">
          <div class="tab tab-main"><a href="./production-inputs.html" class="format-link">INPUTS</a></div>
          <div class="tab"><a href="./production-activities.html" class="format-link">ACTIVITIES</a></div>
          <div class="tab"><a href="./production-calendar.html" class="format-link">CALENDAR</a></div>
      </div>
    </div>
    <all-farm-inputs v-on:show-modal="showModal"/>
    <farm-input-modal v-if="show" v-bind:input="singleInput" v-on:close-modal="closeModal"/>
  </div>
</template>

<script>
import allFarmInputs from './AllFarmInputs.vue';
import farmInputModal from './FarmInputModal.vue';

export default {
  components: {
    allFarmInputs, farmInputModal
  },
  data() {
    return {
      show: false,
      singleInput: {}
    }
  },
  methods: {
    showModal(single) {
      this.show = true;
      this.singleInput = single;
    },
    closeModal() {
      this.show = false;
    },
    closeMenuBar() {
      /* menu */
      const menuButton = document.querySelector('.menu-button');
      const sideBar = document.querySelector('.side-bar');
      const main = document.querySelector('.main');

      /* event listeners */
      sideBar.classList.toggle('open');
      sideBar.classList.toggle('side-bar-close');
      main.classList.toggle('main-shift');
      main.classList.toggle('main-full');
    },
  }
};
</script>
