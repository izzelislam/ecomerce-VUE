<template>
  <div class="home">
    <HeaderShayna />
    <HeroSection />
    <ProductShyna />
    <InstaSyna />
    <PartnerShyna />
    <FooterShyna />
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderShayna from "@/components/HeaderShayna.vue";
import HeroSection from "@/components/HeroSection.vue";
import ProductShyna from "@/components/ProductShyna.vue";
import InstaSyna from "@/components/InstaSyna.vue";
import PartnerShyna from "@/components/PartnerShyna.vue";
import FooterShyna from "@/components/FooterShyna.vue";

export default {
  name: "Home",
  components: {
    HeaderShayna,
    HeroSection,
    ProductShyna,
    InstaSyna,
    PartnerShyna,
    FooterShyna,
  },
};
</script>
