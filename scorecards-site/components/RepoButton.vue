<template>
  <a class="relative flex flex-row justify-center w-130 h-29" :href="`${repoURL}`">
    <GithubRepoIcon class="absolute top-0 left-0" />
    <span class="text-16 top-7 right-1 absolute">{{ stars }}</span>
  </a>
</template>

<script>
import GithubRepoIcon from "@/assets/icons/github-repo.svg?inline";
export default {
  name: "RepoButton",
  components: {
    GithubRepoIcon,
  },
  created() {},
  data() {
    return {
      repoURL: 'https://github.com/ossf/scorecard',
    };
  },
  props: {
    commits: null,
    stars: null,
  },
  methods: {},
};
</script>
