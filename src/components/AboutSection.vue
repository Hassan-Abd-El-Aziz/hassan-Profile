<template>
  <section class="text-white mt-18" id="about">
    <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start">
      <div
        class="h-24 w-64 bg-gradient-to-br from-primary via-secondary blur-2xl to-[#570cac] opacity-20"
      ></div>
    </div>
    <div
      class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 xl:px-16 z-1"
    >
      <div data-aos="flip-right">
        <h2 class="text-4xl font-bold text-white text-left mb-8">
          My Education
        </h2>
        <div class="space-y-8 py-8">
          <div
            v-for="element in education"
            :key="element.id"
            class="flex items-center md:w[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
          >
            <div class="w-1/4">
              <img
                src="https://img.icons8.com/?size=100&id=FtlxxFId8asm&format=png&color=ffffff"
                alt="graduation"
              />
            </div>
            <div class="w-3/4 pl-4">
              <h3
                class="text-2xl font-semibold uppercase bg-clip-text text-transparent bg-gradient-to-r from-primary to-secondary lg:text-xl"
              >
                {{ element.school }}
              </h3>
              <p class="text-white">{{ element.program }}</p>
              <p class="text-white">{{ element.year }}</p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full"
        data-aos="flip-right"
      >
        <h2 class="text-4xl font-bold text-white md:text-center text-left mb-4">
          More
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
            >About</span
          >
          Me
        </h2>
        <p class="text-base lg:text-lg mt-8 py-8">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis
          repellat, cupiditate quo, vero veniam minima eius soluta ab ipsam
          expedita quos, corrupti dolores sint necessitatibus provident quidem
          cumque! Quidem numquam maxime recusandae amet accusamus beatae quasi
          explicabo laudantium pariatur molestiae suscipit iure, sint
          necessitatibus sunt earum est aut! Itaque, velit?
        </p>
        <div class="grid grid-cols-3 gap-4 max-w-lg pt-8">
          <div
            class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3"
          >
            <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
              +50
            </h3>
            <p class="text-sm sm:text-base text-gray-300">Happy client</p>
          </div>

          <div
            class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3"
          >
            <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
              +100
            </h3>
            <p class="text-sm sm:text-base text-gray-300">Project</p>
          </div>

          <div
            class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3"
          >
            <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">
              +2
            </h3>
            <p class="text-sm sm:text-base text-gray-300">Year Experience</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
const education = ref([
  {
    id: 1,
    school: "Egyptian Army - Military Service ",
    program: " software Engineer",
    year: 2023,
  },
  {
    id: 2,
    school: "YAT Academy",
    program: "software Engineer",
    year: 2017,
  },
  {
    id: 3,
    school: "Higher Technological Institute.",
    program: " Management Information Systems",
    year: 2016,
  },
]);
</script>
