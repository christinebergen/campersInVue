<template>
  <!-- icon search account -->
  <div class="w-full h-10" id="topNav">
    <!-- logo -->
    <div class="float-left">
      <div>
        <a href="/"
          ><img
            src="../assets/logo_layered2.png"
            alt="camp logo"
            class="w-12 sm:w-20 rounded-full hover:scale-75 transition-all"
        /></a>
      </div>
    </div>
    <!-- logo -->

    <!-- top bar -->
    <div class="float-right">
      <!-- account icon -->
      <div class="float-right mt-4 md:mt-8">
        <a id="dropdownButton" @click="showlsit()">
          <svg
            class="fill-current text-gray-700 h-6 sm:h-8 w-6 sm:w-8 hover:scale-75 transition-all"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5 5a5 5 0 0 1 10 0v2A5 5 0 0 1 5 7V5zM0 16.68A19.9 19.9 0 0 1 10 14c3.64 0 7.06.97 10 2.68V20H0v-3.32z"
            />
          </svg>
        </a>

        <div
          class="mt-2 origin-top-right absolute right-0 z-10 w-56 rounded-md pr-8 hidden"
        >
          <div class="rounded-md bg-[#7993A0] shadow-xs">
            <div class="py-1">
              <a
                href="/signin"
                class="block px-4 py-2 text-md text-white hover:bg-[#CED9DF]"
                >Sign In / Sign Up</a
              >
              <a
                href="/signin"
                class="block px-4 py-2 text-md text-white hover:bg-[#CED9DF]"
                >Sign Out</a
              >
            </div>
          </div>
        </div>
      </div>
      <!-- icon account -->
    </div>
    <!-- top bar -->
  </div>
  <!-- icon search account -->
</template>

<script setup>
function showlsit() {
  const dropdownButton = document.querySelector("#dropdownButton");
  const dropdownMenu = dropdownButton.nextElementSibling;

  dropdownMenu.classList.toggle("hidden");

  if (
    !dropdownButton.contains(event.target) &&
    !dropdownMenu.contains(event.target)
  ) {
    dropdownMenu.classList.add("hidden");
  }
}
</script>
