<template>
  <v-container class="ma-0 pa-0 d-flex flex-column align-center main-container" fluid>
    <template v-if="$device.isDesktop">
      <desktop-page></desktop-page>
    </template>
    <template v-else-if="$device.isTablet">
      <desktop-page></desktop-page>
    </template>
    <template v-else>
      <mobile-page></mobile-page>
    </template>
  </v-container>
</template>

<script>
import desktop from './desktop.vue';
import mobile from './mobile.vue';

export default {
  components: {
    'desktop-page': desktop,
    'mobile-page': mobile
  },
  data() {
    return {}
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
.main-container {
  height: 100%;
  width: 100%;
}
</style>