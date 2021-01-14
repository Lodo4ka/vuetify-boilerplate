<template>
  <v-card style="margin-bottom: 24px; margin-top: 48px;" v-bind="$attrs" v-on="$listeners">
    <div style="top: -24px; margin-bottom: -24px" class="v-offset">
      <v-card
        elevation="10"
        class="d-flex align-center"
        dark
        min-height="80"
        style="background-color: #3755a8 !important;"
      >
        <div class="px-3">
          <h4 class="title font-weight-light mb-2" v-text="title" />
          <p class="category font-weight-thin mb-0" v-text="text" />
        </div>
      </v-card>
    </div>

    <v-card-text>
      <slot />
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: 'MaterialCard',
  props: {
    color: { type: String, default: 'secondary' },
    title: { type: String, default: undefined },
    text: { type: String, default: undefined },
  },
};
</script>

<style lang="scss" scoped>
.v-offset {
  margin: 0 auto;
  max-width: calc(100% - 32px);
  position: relative;
  z-index: 1;
}
</style>
