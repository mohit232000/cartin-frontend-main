<template>
  <div
    class="flex min-h-full items-center justify-center py-12 px-4 sm:px-6 lg:px-8 border-2"
  >
    <div class="w-full max-w-md space-y-8">
      <div>
        <img
          class="mx-auto h-12 w-auto"
          src="../assets/shop.png"
          alt="Your Company"
        />
        <h2
          class="mt-6 text-center text-3xl font-bold tracking-tight text-gray-900"
        >
          Change Password
        </h2>
      </div>
      <form
        @submit.prevent="reset"
        class="mt-8 space-y-6"
        action="#"
        method="POST"
      >
        <input type="hidden" name="remember" value="true" />
        <div class="-space-y-px rounded-md shadow-sm">
          <div>
            <label
              for="password"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Old Password</label
            >
            <input
              v-model="passwords.oldpass"
              id="password"
              name="password"
              type="password"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <div>
            <label
              for="password1"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >New Password</label
            >
            <input
              v-model="passwords.newpass"
              id="password1"
              name="password1"
              type="password"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
        </div>

        <div>
          <button
            type="submit"
            class="group relative flex w-full justify-center rounded-md border border-transparent bg-sky-500 py-2 px-4 text-sm font-medium text-white hover:bg-sky-600 focus:outline-none focus:ring-2 focus:ring-sky-500 focus:ring-offset-2"
          >
            Change Password
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "RstPass",
  data() {
    return {
      passwords: {
        oldpass: "",
        newpass: "",
      },
    };
  },
  methods: {
    reset() {
      axios
        .post("http://localhost:8080/user/changePassword", {
          userId: localStorage.logged,
          oldPassword: this.passwords.oldpass,
          newPassword: this.passwords.newpass,
        })
        .then(this.goToLogin);
    },
    goToLogin() {
      this.$router.push("/");
    },
  },
};
</script>
