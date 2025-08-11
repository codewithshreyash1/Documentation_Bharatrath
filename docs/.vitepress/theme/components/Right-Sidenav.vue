<template>
  <aside
    v-if="currentLang === 'en'"
    class="quick-links"
    id="quick-links-en"
    aria-label="Quick Links"
  >
    <h2>Quick Links</h2>
    <ul>
      <li>
        <a href="#introduction">Introduction to Bharatrath Digital Platform</a>
      </li>
      <li><a href="#who">Who is it for?</a></li>
      <li><a href="#what">What is Bharatrath?</a></li>
      <li><a href="#how">How to Use</a></li>
      <li><a href="#why">Why Choose Bharatrath?</a></li>
      <li><a href="#examples">Real Examples</a></li>
      <li><a href="#how-to-order">How to order as a customer</a></li>
    </ul>
  </aside>

  <aside
    v-else-if="currentLang === 'hi'"
    class="quick-links"
    id="quick-links-hi"
    aria-label="Quick Links"
  >
    <h2>त्वरित लिंक</h2>
    <ul>
      <li>
        <a href="#introduction-hi">Bharatrath डिजिटल प्लेटफॉर्म का परिचय</a>
      </li>
      <li><a href="#who-hi">यह किसके लिए है?</a></li>
      <li><a href="#what-hi">Bharatrath क्या है?</a></li>
      <li><a href="#how-hi">कैसे उपयोग करें</a></li>
      <li><a href="#why-hi">Bharatrath क्यों चुनें?</a></li>
      <li><a href="#examples-hi">वास्तविक उदाहरण</a></li>
      <li><a href="#how-to-order">ग्राहक के रूप में ऑर्डर कैसे करें</a></li>
    </ul>
  </aside>

  <aside
    v-else
    class="quick-links"
    id="quick-links-mr"
    aria-label="Quick Links"
  >
    <h2>द्रुत दुवे</h2>
    <ul>
      <li>
        <a href="#introduction-mr">Bharatrath डिजिटल प्लॅटफॉर्मचा परिचय</a>
      </li>
      <li><a href="#who-mr">हे कोणासाठी आहे?</a></li>
      <li><a href="#what-mr">Bharatrath म्हणजे काय?</a></li>
      <li><a href="#how-mr">कसा वापर करावा</a></li>
      <li><a href="#why-mr">Bharatrath का निवडावे?</a></li>
      <li><a href="#examples-mr">वास्तविक उदाहरणे</a></li>
      <li><a href="#how-to-order">ग्राहक म्हणून ऑर्डर कसे द्यावे</a></li>
    </ul>
  </aside>
</template>

<script setup>
import { defineProps, watch, ref } from "vue";
const props = defineProps({ lang: String });
const currentLang = ref(props.lang);

watch(
  () => props.lang,
  (val) => {
    currentLang.value = val;
  },
  { immediate: true }
);
</script>
