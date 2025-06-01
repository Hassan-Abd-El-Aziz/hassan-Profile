<template>
  <div class="bg-[#111827] min-h-screen">
    <!-- wrap components in Suspense to handel loading -->
    <Suspence>
      <template #default>
        <!-- wrap all components inside a single root element -->
        <div>
          <NavBar />
          <HeroSection />
          <ServicesSection />
          <AboutSection />
          <ExperienceAndskills />
          <LatestProjSection />
          <ContactSection />
          <TestimonialsSection />
          <Footer />
          <BackToTop />
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <loadingSpinner />
        </div>
      </template>
    </Suspence>
  </div>
</template>
<script setup>
import { defineAsyncComponent } from "vue";
// import Components Asynchronously
const NavBar = defineAsyncComponent(() => import("@/Components/NavBar.vue"));
const HeroSection = defineAsyncComponent(() =>
  import("@/Components/HeroSection.vue")
);
const ServicesSection = defineAsyncComponent(() =>
  import("@/Components/ServicesSection.vue")
);
const AboutSection = defineAsyncComponent(() =>
  import("@/Components/AboutSection.vue")
);
const ExperienceAndskills = defineAsyncComponent(() =>
  import("@/Components/ExperienceAndskills.vue")
);

const LatestProjSection = defineAsyncComponent(() =>
  import("@/Components/LatestProjSectio.vue")
);
const ContactSection = defineAsyncComponent(() =>
  import("@/Components/ContactSection.vue")
);
const TestimonialsSection = defineAsyncComponent(() =>
  import("@/Components/TestimonialsSection.vue")
);
const Footer = defineAsyncComponent(() => import("@/Components/Footer.vue"));
const BackToTop = defineAsyncComponent(() =>
  import("@/Components/BackToTop.vue")
);
import loadingSpinner from "./components/LoadingSpinner.vue";
</script>

<style>
*{
  scrollbar-width: thin;
  scrollbar-color: #111827 #f1f1f1;
}
</style>