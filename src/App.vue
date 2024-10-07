<script>
import HeroSection from "./components/Hero.vue";
import HomeSection from "./components/HomeSection.vue";
import AboutMe from "./components/About.vue";
import MyResume from "./components/Resume.vue";
import MyServices from "./components/Services.vue";
import StatsSection from "./components/Statistics.vue";
import FaqSection from "./components/Faqs.vue";
import ContactSection from "./components/Contact.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  components: {
    HeroSection,
    HomeSection,
    AboutMe,
    MyResume,
    MyServices,
    StatsSection,
    FaqSection,
    ContactSection,
    AppFooter,
  },
};
</script>

<template>
  <div>
    <HeroSection />
    <div class="content">
      <HomeSection />
      <AboutMe />
      <MyResume />
      <MyServices />
      <StatsSection />
      <FaqSection />
      <ContactSection />
      <AppFooter />
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  height: 100%;
}

.content {
  padding-top: 80px;
}
</style>
