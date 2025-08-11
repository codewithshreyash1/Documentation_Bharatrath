<script setup>
import { defineProps, watch, ref } from "vue";
const props = defineProps({ lang: String });
const currentLang = ref(props.lang);
// const currentLang = "hi";

watch(
  () => props.lang,
  (val) => {
    currentLang.value = val;
  },
  { immediate: true }
);
</script>

<template>
  <nav
    v-if="currentLang === 'en'"
    class="sidebar"
    id="sidebar-en"
    aria-label="Navigation"
  >
    <div class="sidebar-section">
      <div class="sidebar-section-title">Introduction</div>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Navigating Bharatrath Digital Platform
      </div>
      <ul class="collapsed">
        <li>
          <a href="#how-to-order" class="sub-topic-link"
            >How customer can place eCommerce orders</a
          >
        </li>
        <li>
          <a href="pos-system.html" class="sub-topic-link"
            >How to use Point of Sale system to place orders</a
          >
        </li>
        <li>
          <a href="admin-panel.html" class="sub-topic-link"
            >Bharatrath Admin Panel - How to Access and walkthrough of
            features</a
          >
        </li>
      </ul>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Initial Setup to Bharatrath Digital Platform
      </div>
      <ul class="collapsed">
        <li>
          <a
            href="#account-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >Account Settings</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#registration" class="sub-topic-link">Registration</a>
            </li>
            <li>
              <a href="#billing-address" class="sub-topic-link"
                >Billing Address</a
              >
            </li>
            <li>
              <a href="#bank-account-details" class="sub-topic-link"
                >Bank Account Details</a
              >
            </li>
            <li>
              <a href="#pos-settings" class="sub-topic-link">POS Settings</a>
            </li>
            <li>
              <a href="#global-features" class="sub-topic-link"
                >Global Features</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#your-business-setup"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >Your Business Setup / System Settings</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-warehouse" class="sub-topic-link"
                >Add a Warehouse / Store</a
              >
            </li>
            <li>
              <a href="#add-categories" class="sub-topic-link"
                >Add Categories</a
              >
            </li>
            <li><a href="#add-brands" class="sub-topic-link">Add Brands</a></li>
            <li>
              <a href="#add-suppliers" class="sub-topic-link">Add Suppliers</a>
            </li>
            <li>
              <a
                href="#add-products"
                class="sub-topic-link has-submenu"
                onclick="toggleNestedSection(this, event)"
                >Add Products</a
              >
              <ul class="nested-collapsed">
                <li>
                  <a href="#add-packs-variants" class="sub-topic-link"
                    >Add Packs / Variants</a
                  >
                </li>
              </ul>
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#delivery-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >Delivery Settings</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#delivery-schedule" class="sub-topic-link"
                >Delivery Schedule</a
              >
            </li>
            <li>
              <a href="#delivery-charge" class="sub-topic-link"
                >Delivery Charge</a
              >
            </li>
            <li>
              <a href="#delivery-zones" class="sub-topic-link"
                >Delivery Zones</a
              >
            </li>
            <li>
              <a href="#assign-delivery-charges" class="sub-topic-link"
                >Assign Delivery Charges to Warehouse/Store</a
              >
            </li>
            <li>
              <a href="#assign-delivery-zone-products" class="sub-topic-link"
                >Assign Delivery Zone to Products</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#setup-pos"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >Setup your Point of Sale</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-pos-register" class="sub-topic-link"
                >Add POS register</a
              >
            </li>
            <li>
              <a href="#assign-pos-access" class="sub-topic-link"
                >Assign POS access to Users</a
              >
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>

  <!-- Hindi Sidebar -->
  <nav
    v-if="currentLang === 'hi'"
    class="sidebar"
    id="sidebar-hi"
    aria-label="Navigation"
  >
    <div class="sidebar-section">
      <div class="sidebar-section-title">परिचय</div>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Bharatrath डिजिटल प्लेटफॉर्म नेविगेशन
      </div>
      <ul class="collapsed">
        <li>
          <a href="#how-to-order" class="sub-topic-link"
            >ग्राहक ई-कॉमर्स ऑर्डर कैसे दे सकते हैं</a
          >
        </li>
        <li>
          <a href="pos-system.html" class="sub-topic-link"
            >पॉइंट ऑफ सेल सिस्टम का उपयोग कैसे करें</a
          >
        </li>
        <li>
          <a href="admin-panel.html" class="sub-topic-link"
            >Bharatrath एडमिन पैनल - पहुंच और सुविधाओं का विवरण</a
          >
        </li>
      </ul>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Bharatrath डिजिटल प्लेटफॉर्म की प्रारंभिक सेटअप
      </div>
      <ul class="collapsed">
        <li>
          <a
            href="#account-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >खाता सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li><a href="#registration" class="sub-topic-link">पंजीकरण</a></li>
            <li>
              <a href="#billing-address" class="sub-topic-link">बिलिंग पता</a>
            </li>
            <li>
              <a href="#bank-account-details" class="sub-topic-link"
                >बैंक खाता विवरण</a
              >
            </li>
            <li>
              <a href="#pos-settings" class="sub-topic-link">POS सेटिंग्स</a>
            </li>
            <li>
              <a href="#global-features" class="sub-topic-link"
                >ग्लोबल फीचर्स</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#your-business-setup"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >आपका व्यवसाय सेटअप / सिस्टम सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-warehouse" class="sub-topic-link"
                >वेयरहाउस / स्टोर जोड़ें</a
              >
            </li>
            <li>
              <a href="#add-categories" class="sub-topic-link"
                >श्रेणियां जोड़ें</a
              >
            </li>
            <li>
              <a href="#add-brands" class="sub-topic-link">ब्रांड जोड़ें</a>
            </li>
            <li>
              <a href="#add-suppliers" class="sub-topic-link"
                >आपूर्तिकर्ता जोड़ें</a
              >
            </li>
            <li>
              <a
                href="#add-products"
                class="sub-topic-link has-submenu"
                onclick="toggleNestedSection(this, event)"
                >उत्पाद जोड़ें</a
              >
              <ul class="nested-collapsed">
                <li>
                  <a href="#add-packs-variants" class="sub-topic-link"
                    >पैक / वेरिएंट जोड़ें</a
                  >
                </li>
              </ul>
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#delivery-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >डिलीवरी सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#delivery-schedule" class="sub-topic-link"
                >डिलीवरी शेड्यूल</a
              >
            </li>
            <li>
              <a href="#delivery-charge" class="sub-topic-link"
                >डिलीवरी चार्ज</a
              >
            </li>
            <li>
              <a href="#delivery-zones" class="sub-topic-link">डिलीवरी जोन्स</a>
            </li>
            <li>
              <a href="#assign-delivery-charges" class="sub-topic-link"
                >वेयरहाउस/स्टोअर को डिलीवरी चार्ज असाइन करें</a
              >
            </li>
            <li>
              <a href="#assign-delivery-zone-products" class="sub-topic-link"
                >उत्पादों को डिलीवरी जोन असाइन करें</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#setup-pos"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >आपका पॉइंट ऑफ सेल सेटअप</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-pos-register" class="sub-topic-link"
                >POS रजिस्टर जोड़ें</a
              >
            </li>
            <li>
              <a href="#assign-pos-access" class="sub-topic-link"
                >उपयोगकर्ताओं को POS एक्सेस असाइन करें</a
              >
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>

  <!-- Marathi Sidebar -->
  <nav
    v-if="currentLang === 'mr'"
    class="sidebar"
    id="sidebar-mr"
    aria-label="Navigation"
  >
    <div class="sidebar-section">
      <div class="sidebar-section-title">परिचय</div>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Bharatrath डिजिटल प्लॅटफॉर्म नेव्हिगेशन
      </div>
      <ul class="collapsed">
        <li>
          <a href="#how-to-order" class="sub-topic-link"
            >ग्राहक ई-कॉमर्स ऑर्डर कसे देऊ शकतात</a
          >
        </li>
        <li>
          <a href="pos-system.html" class="sub-topic-link"
            >पॉइंट ऑफ सेल सिस्टमचा वापर कसा करावा</a
          >
        </li>
        <li>
          <a href="admin-panel.html" class="sub-topic-link"
            >Bharatrath अॅडमिन पॅनेल - प्रवेश आणि वैशिष्ट्यांचा तपशील</a
          >
        </li>
      </ul>
    </div>
    <div class="sidebar-section">
      <div
        class="sidebar-section-title"
        onclick="toggleSection(this)"
        aria-expanded="false"
      >
        Bharatrath डिजिटल प्लॅटफॉर्मची प्रारंभिक सेटअप
      </div>
      <ul class="collapsed">
        <li>
          <a
            href="#account-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >खाते सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li><a href="#registration" class="sub-topic-link">नोंदणी</a></li>
            <li>
              <a href="#billing-address" class="sub-topic-link">बिलिंग पत्ता</a>
            </li>
            <li>
              <a href="#bank-account-details" class="sub-topic-link"
                >बँक खाते तपशील</a
              >
            </li>
            <li>
              <a href="#pos-settings" class="sub-topic-link">POS सेटिंग्स</a>
            </li>
            <li>
              <a href="#global-features" class="sub-topic-link"
                >ग्लोबल फीचर्स</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#your-business-setup"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >तुमचा व्यवसाय सेटअप / सिस्टम सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-warehouse" class="sub-topic-link"
                >वेअरहाउस / स्टोअर जोडा</a
              >
            </li>
            <li>
              <a href="#add-categories" class="sub-topic-link">श्रेणी जोडा</a>
            </li>
            <li><a href="#add-brands" class="sub-topic-link">ब्रँड जोडा</a></li>
            <li>
              <a href="#add-suppliers" class="sub-topic-link">पुरवठादार जोडा</a>
            </li>
            <li>
              <a
                href="#add-products"
                class="sub-topic-link has-submenu"
                onclick="toggleNestedSection(this, event)"
                >उत्पादने जोडा</a
              >
              <ul class="nested-collapsed">
                <li>
                  <a href="#add-packs-variants" class="sub-topic-link"
                    >पॅक / व्हेरिएंट जोडा</a
                  >
                </li>
              </ul>
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#delivery-settings"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >डिलिव्हरी सेटिंग्स</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#delivery-schedule" class="sub-topic-link"
                >डिलिव्हरी शेड्यूल</a
              >
            </li>
            <li>
              <a href="#delivery-charge" class="sub-topic-link"
                >डिलिव्हरी चार्ज</a
              >
            </li>
            <li>
              <a href="#delivery-zones" class="sub-topic-link"
                >डिलिव्हरी झोन्स</a
              >
            </li>
            <li>
              <a href="#assign-delivery-charges" class="sub-topic-link"
                >वेअरहाउस/स्टोअरला डिलिव्हरी चार्ज असाइन करा</a
              >
            </li>
            <li>
              <a href="#assign-delivery-zone-products" class="sub-topic-link"
                >उत्पादनांना डिलिव्हरी झोन असाइन करा</a
              >
            </li>
          </ul>
        </li>

        <li>
          <a
            href="#setup-pos"
            class="sub-topic-link has-submenu"
            onclick="toggleNestedSection(this, event)"
            >तुमचा पॉइंट ऑफ सेल सेटअप</a
          >
          <ul class="nested-collapsed">
            <li>
              <a href="#add-pos-register" class="sub-topic-link"
                >POS रजिस्टर जोडा</a
              >
            </li>
            <li>
              <a href="#assign-pos-access" class="sub-topic-link"
                >वापरकर्त्यांना POS अॅक्सेस असाइन करा</a
              >
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>
</template>
