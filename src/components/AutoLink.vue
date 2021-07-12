<template>
  <a v-if="isExternal" target="_blank" rel="noopener noreferrer" :class="externalLinkClass" :href="to"><slot />
  <!-- <i v-if="!externalLinkClass">➚</i> -->
  </a>
  <router-link v-else v-bind="$props"><slot /></router-link>
</template>
<script>
import { RouterLink } from "vue-router";
export default {
  props: { ...RouterLink.props, externalLinkClass: {type: String, default: ''} },
  components: {
    RouterLink
  },
  computed:{
    isExternal(){
      return typeof this.to === 'string' && this.to.startsWith('http')
    }
  }
};
</script>