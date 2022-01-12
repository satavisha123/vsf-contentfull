<template>
  <div>
    <div v-if="loading">Loading content...</div>
    <div v-if="error">error</div>
  <div v-if="content">

      <render-content :content="content" />
  </div>
  
  </div>
</template>

<script>
import { onSSR } from "@vue-storefront/core";
import { useContent } from "@vsf-enterprise/contentful";
// These are the components that will be rendered by RenderContent

import Banner from "~/components/cms/Banner";
import RenderContent from "~/components/cms/RenderContent.vue";

export default {
  name:"Home",
  components: {
    RenderContent,
    Banner,
  },
  setup() {
 
    const { search, content, loading, error } = useContent();
    // fetch data
    onSSR(async () => {
      await search({ id: "2PHdWS1Ud0QPEfXjvjqwB6" });
    console.log("sata",content.value)
    });
    // return data
    return {
      content,
      loading,
      error,
    };
  },
};
</script>