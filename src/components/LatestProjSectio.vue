<template>
  <section class="text-white mt-20" id="projects">
    <div class="px-4 xl:pl-16">
      <div class="mb-4 md:flex md:justify-between xl:pr-16">
        <h2 class="text-4xl font-bold text-white">my Latest Projects</h2>
        <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
          <button
            class="hover:text-primary"
            v-for="category in ['all', 'web development', 'mobile App']"
            :key="category"
            @click="() => (SelectedCategory = category)"
          >
            {{ category }}
          </button>
        </div>
      </div>
      <ul
        class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-10 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
        data-aos="fade-right"
      >
        <div
          v-for="project in filteredProjects"
          :key="project.id"
          class="hover:scale-105 transition-all ease-in-out cursor-pointer"
        >
          <div
            class="h-52 md:h-[24rem] rounded-t-xl relative group"
            :style="{
              backgroundImage: 'url(' + project.Image + ')',
              backgroundSize: 'cover',
            }"
          ></div>

          <div
            class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0 hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500"
          ></div>
          <div
            class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4"
          >
            <h3
              class="text-lg font-semibold uppercase flex justify-center lg:text-xl"
            >
              {{ project.title }}
            </h3>
            <p class="text-[#ADB7BE]">{{ project.description }}</p>
            <div class="flex flex-wrap p-2.5 justify-center">
              <div
                v-for="technolgy in project.technologies"
                :key="technolgy"
                class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                style="
                  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
                  border: 1px solid #111827;
                  backdrop-filter: blur(9px);
                  -webkit-backdrop-filter: blur(9px);
                "
              >
                <p class="px-1 py-2">{{ technolgy }}</p>
              </div>
            </div>
          </div>
        </div>
      </ul>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";

const Projects = ref([
  {
    id: 1,
    category: "web development",
    Image: "src/assets/web1.jpg",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
  {
    id: 2,
    category: "mobile App",
    Image: "src/assets/mob1.jpg",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
  {
    id: 3,
    category: "web development",
    Image: "src/assets/web2.jpg",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
  {
    id: 4,
    category: "mobile App",
    Image: "src/assets/mob2.jpg",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
  {
    id: 5,
    category: "web development",
    Image: "src/assets/cofe.png",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
  {
    id: 6,
    category: "mobile App",
    Image: "src/assets/mob1.jpg",
    title: "project 1",
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Est voluptas aut officiis quam eaque doloribus saepe qui soluta rerum corrupti perferendis ipsum libero, accusantium consequatur sunt impedit. Repellat, porro rerum!",
    technologies: ["vue.js 3", "vuex", "Express"],
    gitURL: "",
    webURL: "",
  },
]);

const SelectedCategory = ref("all");
const filteredProjects = computed(() => {
  if (SelectedCategory.value === "all") {
    return Projects.value;
  }
  return Projects.value.filter(
    (project) =>
      project.category.toLocaleLowerCase() ===
      SelectedCategory.value.toLocaleLowerCase()
  );
});
</script>
