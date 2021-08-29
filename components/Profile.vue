<template>
  <div class="wrapper">
    <h1 class="pageTitle">このブログについて</h1>
    <div
      v-if="profile.description"
      class="description"
      v-html="profile.description"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    profile: {
      type: Object,
      required: false,
      default: undefined,
    },
    id: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.wrapper {
  margin-top: 24px;
}

.pageTitle {
  font-size: 20px;
  font-weight: bold;
  background-color: #eee;
  padding: 6px 10px;
  margin-bottom: 10px;
  border-radius: 5px;
}

.description {
  & >>> a {
    color: var(--color-purple);
    text-decoration: underline;
    word-wrap: break-word;
    word-break: break-all;
  }
}

@media (max-width: 1160px) {
  .wrapper {
    text-align: center;
  }
}
</style>
