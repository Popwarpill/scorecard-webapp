<template>
  <div class="theme-code-block" :class="{ 'theme-code-block__active': active }">
    <slot />
  </div>
</template>

<script>
export default {
  name: "CodeBlock",
  props: {
    title: {
      type: String,
      required: true,
    },
    active: {
      type: Boolean,
      default: false,
    },
    single: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {
    if (this.$parent && this.$parent.loadTabs) {
      this.$parent.loadTabs();
    }
  },
};
</script>

<style lang="scss" scoped>
.theme-code-block {
  display: none;

  & .nuxt-content-highlight > pre {
    border-bottom-left-radius: 0.5em;
    border-bottom-right-radius: 0.5em;
    border-top: 2px solid #302825;
    background-color: black;
    padding: 1.1em;
    margin-bottom: 0;
    & > code {
      padding: 0;
    }
  }
}
.theme-code-block__active {
  display: block;
}
.theme-code-block > pre {
  background-color: orange;
}
</style>
