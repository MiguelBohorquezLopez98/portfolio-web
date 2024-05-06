<template>
  <div>
    <NavBar v-if="!isMobile" />
    <NavBarResponsive v-else />
  </div>
</template>

<script>
import { defineComponent } from 'vue';

// Components
import NavBar from '../components/NavBar.vue';
import NavBarResponsive from '../components/NavBarResponsive.vue';

export default defineComponent({
  name: 'HomeView',

  components: {
    NavBar,
    NavBarResponsive,
  },

  data() {
    return {
      windowWidth: window.innerWidth
    };
  },

  computed: {
    isMobile() {
      return this.windowWidth <= 600;
    }
  },

  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth;
    }
  },

  mounted() {
    window.addEventListener('resize', this.handleResize);
  },

  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  }
});
</script>

<style src="../assets/css/styles.css"></style>
