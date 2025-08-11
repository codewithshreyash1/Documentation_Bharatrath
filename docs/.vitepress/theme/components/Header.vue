<template>
  <header class="header">
    <button class="menu-toggle" aria-label="Toggle navigation menu">
      <span></span>
      <span></span>
      <span></span>
    </button>
    <h1 class="class-h1">Bharatrath Documentation</h1>
    <div
      id="main-language-selector"
      role="region"
      aria-label="Language selection"
    >
      <span>Language:</span>
      <button
        id="lang-btn-en"
        :aria-pressed="lang === 'en'"
        @click="setLanguage('en')"
      >
        English
      </button>
      <button
        id="lang-btn-hi"
        :aria-pressed="lang === 'hi'"
        @click="setLanguage('hi')"
      >
        हिंदी
      </button>
      <button
        id="lang-btn-mr"
        :aria-pressed="lang === 'mr'"
        @click="setLanguage('mr')"
      >
        मराठी
      </button>
      <select
        v-model="lang"
        aria-label="Select language"
        @change="setLanguage($event.target.value)"
      >
        <option value="en">English</option>
        <option value="hi">हिंदी</option>
        <option value="mr">मराठी</option>
      </select>
    </div>
    <div class="contact-links desktop-only">
      <span>
        Website:
        <a href="https://www.bharatrath.com" target="_blank"
          >www.bharatrath.com</a
        >
      </span>
      <span>
        Support Email:
        <a href="mailto:support@bharatrath.com">support@bharatrath.com</a>
      </span>
    </div>
    <div class="search-bar" role="search" aria-label="Search documentation">
      <input
        type="text"
        placeholder="Search..."
        aria-label="Search documentation"
      />
    </div>
  </header>
</template>

<script setup>
import { ref, watch, defineProps, defineEmits } from "vue";
const props = defineProps({ lang: String });
const emit = defineEmits(["lang-change"]);
const lang = ref(props.lang);

watch(
  () => props.lang,
  (val) => {
    lang.value = val;
  }
);

function setLanguage(l) {
  lang.value = l;
  emit("lang-change", l);
}
</script>
