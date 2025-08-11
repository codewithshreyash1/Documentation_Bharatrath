<template>
  <div>
    <Header :lang="lang" @lang-change="handleLangChange" />
    <main class="container">
      <LeftSidenav :lang="lang" />
      <Content />
      <RightSidenav :lang="lang" />
    </main>
    <Footer />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import LeftSidenav from "./components/Left-Sidenav.vue";
import RightSidenav from "./components/Right-Sidenav.vue";

const lang = ref("en");
function handleLangChange(newLang: string) {
  console.log("Language changed to:", newLang);
  lang.value = newLang;
}
</script>
