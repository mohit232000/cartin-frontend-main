<!-- 
<template>
 <div class="mt-10 sm:mt-0">
    <div class="md:grid md:grid-cols-3 md:gap-6">
      <div class="mt-5 md:col-span-2 md:mt-0">
        <form action="#" method="POST">
          <div class="overflow-hidden shadow sm:rounded-md">
            <div class="bg-white px-4 py-5 sm:p-6">
              <div class="grid grid-cols-6 gap-6">
                <div class="col-span-6 sm:col-span-3">
                  <label for="first-name" class="block text-sm font-medium text-gray-700">Name</label>
                  <input type="text" name="first-name" id="first-name" autocomplete="given-name" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-sky-500 focus:ring-sky-500 sm:text-sm" />
                </div>
                <div class="col-span-6 sm:col-span-4">
                  <label for="email-address" class="block text-sm font-medium text-gray-700">Email address</label>
                  <input type="text" name="email-address" id="email-address" autocomplete="email" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-sky-500 focus:ring-sky-500 sm:text-sm" />
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="phone" class="block text-sm font-medium text-gray-700">Phone Number</label>
                  <input type="text" name="phone" id="phone" autocomplete="" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-sky-500 focus:ring-sky-500 sm:text-sm" />
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="gender" class="block text-sm font-medium text-gray-700">Gender</label>
                  <select id="gender" name="gender" autocomplete="" class="mt-1 block w-full rounded-md border border-gray-300 bg-white py-2 px-3 shadow-sm focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm">
                    <option>Male</option>
                    <option>Female</option>
                    <option>Other</option>
                  </select>
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
                  <input type="password" name="password" id="password" autocomplete="" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-sky-500 focus:ring-sky-500 sm:text-sm" />
                </div>
                <div class="col-span-6 sm:col-span-3">
                  <label for="password1" class="block text-sm font-medium text-gray-700">Confirm Password</label>
                  <input type="password" name="password1" id="password1" autocomplete="" class="mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-sky-500 focus:ring-sky-500 sm:text-sm" />
                </div>
              </div>
            </div>
            <div class="bg-gray-50 px-4 py-3 text-right sm:px-6">
              <button type="submit" class="inline-flex justify-center rounded-md border border-transparent bg-sky-600 py-2 px-4 text-sm font-medium text-white shadow-sm hover:bg-sky-700 focus:outline-none focus:ring-2 focus:ring-sky-500 focus:ring-offset-2">Create Account</button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import FormInput from './FormInput.vue';
export default {
  name: 'SignUp'
}
</script> -->
<!--
  This example requires some changes to your config:
  
  ```
  // tailwind.config.js
  module.exports = {
    // ...
    plugins: [
      // ...
      require('@tailwindcss/forms'),
    ],
  }
  ```
-->
<template>
  <!--
    This example requires updating your template:

    ```
    <html class="h-full bg-gray-50">
    <body class="h-full">
    ```
  -->
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
          Create your account
        </h2>
      </div>
      <form
        @submit.prevent="createUser"
        class="mt-8 space-y-6"
        action="#"
        method="POST"
      >
        <input type="hidden" name="remember" value="true" />
        <div class="-space-y-px rounded-md shadow-sm">
          <div>
            <label
              for="fname"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >First Name</label
            >
            <input
              v-model="signup_data.firstName"
              id="fname"
              name="fname"
              type="text"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <div>
            <label
              for="lname"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Last Name</label
            >
            <input
              v-model="signup_data.lastName"
              id="lname"
              name="lname"
              type="text"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <div>
            <label
              for="email"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Email</label
            >
            <input
              v-model="signup_data.email"
              id="email"
              name="email"
              type="email"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <div>
            <label
              for="password"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Password</label
            >
            <input
              v-model="signup_data.password"
              id="password"
              name="password"
              type="password"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <!-- <div>
            <label for="password1" class="block text-sm font-medium text-gray-700 pt-4 pb-3">Confirm password</label>
            <input v-model="signup_data.password1" id="password1" name="password1" type="password" autocomplete="" required="" class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm" placeholder="" />
          </div> -->
          <div>
            <label
              for="address"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Address</label
            >
            <input
              v-model="signup_data.address"
              id="address"
              name="address"
              type="text"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
          <div>
            <label
              for="phone"
              class="block text-sm font-medium text-gray-700 pt-4 pb-3"
              >Phone number</label
            >
            <input
              v-model="signup_data.phone"
              id="phone"
              name="phone"
              type="tel"
              autocomplete=""
              required=""
              class="relative block w-full appearance-none rounded-none rounded-t-md border border-gray-300 px-3 py-2 text-gray-900 placeholder-gray-500 focus:z-10 focus:border-sky-500 focus:outline-none focus:ring-sky-500 sm:text-sm"
              placeholder=""
            />
          </div>
        </div>

        <div class="flex items-center justify-between">
          <div class="text-sm">
            <a href="/login" class="font-medium text-sky-500 hover:text-sky-600"
              >Already have an account?</a
            >
          </div>
        </div>

        <div>
          <button
            type="submit"
            class="group relative flex w-full justify-center rounded-md border border-transparent bg-sky-500 py-2 px-4 text-sm font-medium text-white hover:bg-sky-600 focus:outline-none focus:ring-2 focus:ring-sky-500 focus:ring-offset-2"
          >
            Create Account
          </button>
          <div
            v-if="addmoney"
            class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex"
          >
            <InitWallet></InitWallet>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import InitWallet from "@/components/InitWallet.vue";
import { LockClosedIcon } from "@heroicons/vue/20/solid";
export default {
  data() {
    return {
      signup_data: {
        firstName: "",
        lastName: "",
        email: "",
        dob: "2003-08-08",
        amount: 1000,
        phone: "",
        address: "",
        password: "",
      },
      addmoney: false,
    };
  },
  components: { InitWallet },
  methods: {
    createUser() {
      axios
        .post("http://localhost:8080/user/signup", this.signup_data)
        .then((response) => {
          this.addMoney();
        });
    },
    addMoney() {
      this.addmoney = !this.addmoney;
    },
  },
};
</script>
