<template>
  <div>
    <slot :linkStyling="linkStyling">
      <router-link :to="{ name: toLink }" :class="linkStyling">
        <span v-if="title" class="mr-2">{{ title }}</span>
        <span v-if="subtitle" class="mr-2 text-white opacity-54">{{
          subtitle
        }}</span>
        <img :src="arrowForward" />
      </router-link>
    </slot>
    <hr class="border-white opacity-12" />
  </div>
</template>

<script>
import arrowForward from '@/assets/arrow-forward.png';

export default {
  name: 'SettingsButton',
  props: {
    title: {
      type: String,
      default: ''
    },
    subtitle: {
      type: String,
      default: ''
    },
    toLink: {
      type: String,
      default: '/'
    }
  },
  data() {
    return {
      arrowForward
    };
  },
  computed: {
    linkStyling() {
      return 'w-full block flex-grow justify-between flex h-full items-center cursor-pointer select-none px-4 pr-6 py-5';
    }
  }
};
</script>
