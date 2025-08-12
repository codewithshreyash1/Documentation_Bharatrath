<template>
  <div class="main">
    <div>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum eius quod
      assumenda pariatur iure quasi ipsa. Voluptatibus nobis tempora doloribus
      omnis. Deleniti blanditiis repellat cumque explicabo perspiciatis
      similique earum quis?
    </div>
    <div>
      <h1>{{ data.title }}</h1>
      <p>{{ data.content }}</p>
      <p>Language: {{ lang }}</p>
      <p>Slug: {{ data.slug }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

const props = defineProps<{
  lang: string;
  data: {
    slug: string;
    title: string;
    lang: string;
    content: string;
  };
}>();
</script>
