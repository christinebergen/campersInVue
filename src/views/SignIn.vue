<template>
  <div class="mx-8 my-8">
    <!-- logo -->
    <div class="float-left">
      <div class="pb-6">
        <a href="/"
          ><img
            src="../assets/logo_layered2.png"
            alt="camp logo"
            class="w-12 sm:w-20 rounded-full hover:scale-75 transition-all"
        /></a>
      </div>
    </div>
    <!-- logo -->

    <!-- sign in -->
    <div class="clear-both flex items-center justify-center mx-8">
      <div class="w-full md:w-8/12 bg-[#7993A0] py-12 md:py-16 rounded-xl mt-6">
        <form action="">
          <!-- title -->
          <h1
            class="flex justify-center text-3xl md:text-4xl pb-8 md:pb-10 text-white"
          >
            Welcome Back!
          </h1>

          <!-- email -->
          <div class="flex justify-center pb-4 md:pb-6">
            <input
              class="rounded-md text-lg md:text-xl py-1 md:py-3 w-full mx-20 md:mx-32 pl-8"
              type="email"
              name="email"
              placeholder="Email"
              required
            />
          </div>

          <!-- password -->
          <div class="flex justify-center pb-4 sm:pb-6">
            <input
              class="rounded-md text-lg md:text-xl py-1 md:py-3 w-full mx-20 md:mx-32 pl-8"
              type="password"
              name="password"
              placeholder="Password"
              required
            />
          </div>

          <!-- sign in button -->
          <div class="flex justify-center rounded-md pb-4 md:pb-6">
            <button
              class="bg-[#3E563E] rounded-md text-md md:text-lg py-0 md:py-1 px-8 md:px-20 text-white hover:bg-[#93A889]"
            >
              Sign In
            </button>
          </div>

          <a
            class="flex justify-center underline pb-2 text-sm md:text-md text-white"
            href=""
            >Or login with Google</a
          >

          <div class="flex justify-center">
            <button
              class="underline text-sm md:text-md text-white"
              id="open-modal-button"
            >
              Sign up
            </button>
          </div>
        </form>
      </div>

      <!-- sign up modal -->
      <div>
        <div
          id="signup-modal" @click="signupModal"
          class="fixed top-32 md:top-60 left-0 right-0 bottom-0 w-48 md:w-80 h-80 md:h-96 mx-auto hidden"
        >
          <div class="bg-[#CED9DF] p-6 rounded-lg">
            <form>
              <h2 class="text-center pb-4 font-bold text-lg">Sign Up</h2>

              <input
                type="email"
                class="w-full border border-gray-400 p-2 mb-4 rounded-lg"
                placeholder="Email"
              />
              <input
                type="password"
                class="w-full border border-gray-400 p-2 mb-4 rounded-lg"
                placeholder="Password"
              />

              <div class="flex justify-center">
                <button
                  class="bg-[#3E563E] text-white py-2 px-4 rounded-xl hover:bg-[#93A889]"
                  id="signup-modal"
                >
                  Sign Up
                </button>
              </div>
            </form>
          </div>
        </div>
        <!-- sign up modal -->
      </div>
    </div>
    <!-- sign in -->
  </div>
</template>

<script setup>
import top from "../components/Top.vue";

// const openModalButton = document.getElementById("open-modal-button");
// const signupModal = document.getElementById("signup-modal");

// openModalButton.addEventListener("click", () => {
//   signupModal.classList.remove("hidden");
// });

// signupModal.addEventListener("click", (event) => {
//   if (event.target === signupModal) {
//     signupModal.classList.add("hidden");
//   }
// });

</script>
