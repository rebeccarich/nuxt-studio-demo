<template>
  <figure class="c-image">
    <h6 v-if="title" class="title">{{ title }}</h6>
    <NuxtLink v-if="link" :to="link" target="_blank">
      <img :src="`/images/${image}`" :alt="alt" />
    </NuxtLink>
    <img v-else :src="`/images/${image}`" :alt="alt" />
    <figcaption v-if="caption">
      {{ caption }}
    </figcaption>
  </figure>
</template>

<script lang="ts" setup>
defineProps({
  image: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    required: false,
  },
  title: {
    type: String,
    required: false,
  },
  caption: {
    type: String,
    required: false,
  },
  link: {
    type: String,
    required: false,
  },
});
</script>

<style lang="scss" scoped>
.c-image {
  img {
    border: 1px solid black;
    max-width: 100%;
    max-height: 100%;
  }

  .title {
    font-weight: 500;
    font-size: 16px;
    line-height: 28px;
    margin-bottom: 20px;
  }

  figcaption {
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    color: black;
    margin-top: 10px;
  }
}
</style>
