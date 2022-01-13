<template>
<div>
  {{$props}}
  <SfBanner
    :title="title"
    :subtitle="subtitle"
    :description="description"
    :button-text="button_text"
    :link="button_link"
    
    :background="background"
  >
    <template #call-to-action>
      <SfButton class="desktop-only" v-if="button_link">
        <nuxt-link :to="{ path: button_link }" class="text-light">
          {{ button_text }}
        </nuxt-link>
      </SfButton>
    </template>
  </SfBanner>
</div>
</template>

<script lang="ts">
import Vue from "vue";
import { SfBanner, SfButton } from "@storefront-ui/vue";

export default Vue.extend({
  name: "Banner",
  components: {
    SfBanner,
    SfButton,
  },
  props: {
    title: {
      type: String,
    },
    subtitle: {
      type: String,
    },
    description: {
      type: String,
    },
    button_text: {
      type: String,
    },
    button_link: {
      type: String,
    },
   
    background: {
      type: String,
    },
  },
});
</script>