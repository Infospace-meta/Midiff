<template>
  <div class="min-h-screen bg-white">
    <ContactNav />
    <Header :isFixed="isHeaderFixed" />
    <div class="" @scroll="handleScroll">
      <RouterView />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import { ref } from "vue";
import { RouterView } from "vue-router";
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import ContactNav from "./components/navbar/navcontact.vue";

const isHeaderFixed = ref(false);

const handleScroll = () => {
  isHeaderFixed.value = window.scrollY > 0;
};

window.addEventListener("scroll", handleScroll);
</script>

<!-- <template>
  <div class="min-h-screen bg-white">
    <Header />
    <div class="mt-16">
      <RouterView />
    </div>
    <Footer />
  </div>
</template>

<script setup>
import { RouterView } from "vue-router";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
</script>

<style scoped></style> -->
