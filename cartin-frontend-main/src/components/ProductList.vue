<template>
  <div v-cloak class="bg-white">
    <div
      class="mx-auto max-w-2xl py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8"
    >
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">
        {{ dash }}
      </h2>

      <div
        class="mt-6 grid grid-cols-1 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8"
      >
        <div
          v-for="prod in product"
          :key="prod.productId"
          class="group relative"
        >
          <div
            class="min-h-80 aspect-w-1 aspect-h-1 w-full overflow-hidden rounded-md bg-gray-200 group-hover:opacity-75 lg:aspect-none lg:h-80"
          >
            <img
              :src="prod.image"
              class="h-full w-full object-cover object-center lg:h-full lg:w-full"
            />
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-sm text-gray-700">
                <a :href="product.href">
                  <span
                    @click="this.$router.push('/productedit/' + prod.productId)"
                    aria-hidden="true"
                    class="absolute inset-0"
                  />
                  <p text-lg>{{ prod.name }}</p>
                </a>
              </h3>
              <p class="mt-1 text-sm text-gray-500">
                {{ prod.description }}
              </p>
              <p class="text-sm font-medium text-gray-900">
                Stock: {{ prod.quantity }}
              </p>
            </div>
            <p class="text-sm font-medium text-gray-900">₹{{ prod.price }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
export default {
  name: "ProductList",
  components: { Navbar, Footer },
  props: ["dash"],
  data() {
    return {
      product: [],
      dash: "Loading products...",
    };
  },
  async mounted() {
    const response = await axios.get("http://localhost:8080/user/products");
    this.product = response.data;
    this.dash = "All products:";
  },
  methods() {
    editProduct(p_id);
    {
      this.$router.push("/productedit/" + p_id);
    }
  },
};
</script>
