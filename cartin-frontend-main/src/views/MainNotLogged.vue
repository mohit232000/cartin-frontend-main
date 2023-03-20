<template>
  <NotLoggedNavbar></NotLoggedNavbar>
  <div class="max-h-15">
    <Carousel></Carousel>
  </div>
  <div class="bg-gray-100">
    <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
      <div class="mx-auto max-w-2xl py-16 sm:py-24 lg:max-w-none lg:py-32">
        <h2 class="text-2xl font-bold text-gray-900">Shop by Category:</h2>

        <div
          class="mt-6 space-y-12 lg:grid lg:grid-cols-5 lg:gap-x-6 lg:space-y-0"
        >
          <div
            v-for="callout in callouts"
            :key="callout.name"
            class="group relative"
          >
            <div
              class="relative h-80 w-full overflow-hidden rounded-lg bg-white group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1"
            >
              <img
                :src="callout.imageSrc"
                :alt="callout.imageAlt"
                class="h-full w-full object-cover object-center"
              />
            </div>
            <h2 class="mt-6 text-lg text-black-500">
              <a :href="callout.href">
                <span class="absolute inset-0" />
                {{ callout.name }}
              </a>
            </h2>
            <!-- <p class="text-base font-semibold text-gray-900">{{ callout.description }}</p> -->
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer></Footer>
</template>

<script>
import NotLoggedNavbar from "../components/NotLoggedNavbar.vue";
import Footer from "../components/Footer.vue";
import Carousel from "../components/Carousel.vue";
import { ref } from "vue";

export default {
  name: "MainNotLogged",
  components: { NotLoggedNavbar, Footer, Carousel },
  data() {
    return {
      callouts: [
        {
          name: "Home Appliances",
          description: "Home Appliances",
          imageSrc:
            "https://www.kindpng.com/picc/m/61-612761_home-appliance-png-file-home-appliances-png-transparent.png",
          imageAlt:
            "Desk with leather desk pad, walnut desk organizer, wireless keyboard and mouse, and porcelain mug.",
          href: "/prodsearchbycat/0",
        },
        {
          name: "Stationery",
          description: "Stationery",
          imageSrc:
            "https://www.kindpng.com/picc/m/65-651840_notebook-png-image-hd-stationary-images-png-transparent.png",
          imageAlt:
            "Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant.",
          href: "/prodsearchbycat/1",
        },
        {
          name: "Groceries",
          description: "Groceries",
          imageSrc:
            "https://www.kindpng.com/picc/m/205-2053317_transparent-grocery-shopping-clipart-grocery-bag-transparent-background.png",
          imageAlt:
            "Collection of four insulated travel bottles on wooden shelf.",
          href: "/prodsearchbycat/2",
        },
        {
          name: "Food",
          description: "Food",
          imageSrc:
            "https://www.kindpng.com/picc/m/326-3264859_lays-image-download-hd-png-download.png",
          imageAlt:
            "Collection of four insulated travel bottles on wooden shelf.",
          href: "/prodsearchbycat/3",
        },
        {
          name: "Miscellaneous",
          description: "Miscellaneous",
          imageSrc:
            "https://media.gettyimages.com/id/458984207/photo/toiletries-and-hygiene-products.jpg?s=612x612&w=gi&k=20&c=Eu5hKAtogjzMoQCfJ_4THQWL3J2SWdqQqWkVHPPldDw=",
          imageAlt:
            "Collection of four insulated travel bottles on wooden shelf.",
          href: "/prodsearchbycat/4",
        },
      ],
    };
  },
};
</script>
