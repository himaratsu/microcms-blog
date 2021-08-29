<template>
  <div class="wrapper">
    <h1 class="pageTitle">つくったもの</h1>
    <ul>
      <li v-for="work in works" :key="work.id" class="list">
        <a v-bind:href="work.link" class="link" target="_blank"
          >{{ work.title }}
        </a>

        <a v-bind:href="work.link" target="_blank">
          <picture v-if="work.image">
            <source
              type="image/webp"
              :data-srcset="work.image.url + '?fit=crop&w=100&h=100&fm=webp'"
            />
            <img
              :data-src="work.image.url + '?fit=crop&w=100&h=100&q=100'"
              class="image lazyload"
              alt
            />
          </picture>
        </a>

        <div class="description">
          {{ work.description }}
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    works: {
      type: Array,
      required: false,
      default: () => [],
    },
  },
};
</script>

<style scoped>
@media (min-width: 1160px) {
  .wrapper {
    padding: 40px 0 0;
  }

  .pageTitle {
    font-size: 20px;
    font-weight: bold;
    background-color: #eee;
    padding: 6px 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }

  .list {
    border-bottom: 1px solid #eee;

    a {
      display: block;
      padding: 10px 0px 0px;
      font-weight: bold;

      /* color: var(--color-purple); */
      text-decoration: underline;
      word-wrap: break-word;
      word-break: break-all;
    }

    &:last-child {
      border-bottom: none;
    }
  }

  .link {
    /* margin-bottom: 4px; */
  }

  .image {
    /* border-radius: 50%; */
    border-radius: 8px;
    width: 64px;
    height: 64px;
    margin-right: 20px;
    margin-bottom: 8px;
  }

  .description {
    font-size: 14px;
    margin-bottom: 32px;
  }
}
@media (min-width: 820px) and (max-width: 1160px) {
  .wrapper {
    padding: 40px 0 0;
  }

  .pageTitle {
    font-size: 20px;
    font-weight: bold;
    background-color: #eee;
    padding: 6px 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }

  .list {
    border-bottom: 1px solid #eee;

    a {
      display: block;
      padding: 10px;
    }

    &:last-child {
      border-bottom: none;
    }
  }
}
@media (max-width: 820px) {
  .wrapper {
    padding: 40px 0 0;
  }

  .pageTitle {
    font-size: 20px;
    font-weight: bold;
    background-color: #eee;
    padding: 6px 10px;
    margin-bottom: 10px;
    border-radius: 5px;
  }

  .list {
    border-bottom: 1px solid #eee;

    a {
      display: block;
      padding: 10px;
    }

    &:last-child {
      border-bottom: none;
    }
  }
}
</style>
