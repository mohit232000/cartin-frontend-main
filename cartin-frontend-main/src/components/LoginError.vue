<template>
  <div class="py-6 px-6 lg:px-8">
    <h2 class="mb-4 text-xl font-medium text-gray-900 dark:text-white">
      Error!
    </h2>
    <div>
      <h3>User does not exist! Create your account:</h3>
    </div>
    <br /><br /><br /><br /><br />
    <button
      @click="goToAccount"
      type="button"
      class="w-full text-white bg-sky-500 hover:bg-sky-600 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-sky-500 dark:hover:bg-sky-400 dark:focus:ring-sky-600"
    >
      Create Account
    </button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "LoginError",
  data() {
    return {};
  },
  methods: {
    goToAccount() {
      this.$router.push("/signup");
    },
  },
};
</script>
