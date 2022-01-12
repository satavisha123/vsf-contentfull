<template>
  <Homenew :component="component" :url="url" :content="content" />
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Homenew",
  props: {
    component: {},
    url: {},
    content: {},
  },
});
</script>
