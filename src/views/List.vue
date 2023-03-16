<template>
  <div class="mx-8 my-8">

    <div>
      <top></top>
    </div>

    <!-- main container -->
    <div class="clear-both grid grid-cols-1 md:grid-cols-2 gap-16">
      <!-- left side -->
      <div class="py-0 md:py-8 mt-8 md:mt-0">
        <!-- to bring -->
        <div>
          <h1 class="font-bold text-xl">To Bring</h1>

          <lo class="marker:text-[#174140] marker:text-2xl text-xl">
            <li>Trip one</li>
            <li>Trip two</li>
          </lo>

          <!-- add activity -->
          <div>
            <button href="" id="add" class="flex flex-row gap-2 mt-3">
              <h3>Add Item</h3>
              <div
                class="flex justify-center bg-[#7993A0] w-6 py-1 rounded-full"
              >
                <span>
                  <svg
                    class="h-4 w-4"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M12 5V19M5 12H19"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </span>
              </div>
            </button>

            <div
              id="create"
              class="fixed top-20 md:top-48 left-0 right-0 bottom-0 mx-auto w-full md:w-1/3 px-10 py-10 hidden"
            >
              <div class="bg-[#7993A0] p-6 rounded-lg">
                <form class="">
                  <h2 class="text-center pb-4 font-bold text-lg">
                    Add a new item
                  </h2>

                  <div>
                    <label class="float-left" for="title">Title</label>
                    <input class="float-right w-1/3" type="text" name="title" />
                  </div>

                  <div class="pt-8">
                    <label for="person" class="float-left"
                      >Who will bring it</label
                    >
                    <input
                      class="float-right w-1/3"
                      type="text"
                      name="person"
                    />
                  </div>

                  <div class="pt-8">
                    <label for="description">Description</label>
                    <br />
                    <textarea
                      class="w-full"
                      name="description"
                      cols="20"
                      rows="5"
                    ></textarea>
                  </div>

                  <div class="flex justify-center pt-4">
                    <button
                      class="bg-[#3E563E] text-white py-2 px-4 rounded-xl hover:bg-[#93A889]"
                    >
                      Save
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
          <!-- add activity -->
        </div>
        <!-- to bring -->

        <!-- Activities -->
        <div class="mt-8">
          <h1 class="font-bold text-xl">Activities</h1>

          <lo class="marker:text-[#174140] marker:text-2xl text-xl">
            <li>Trip one</li>
            <li>Trip two</li>
          </lo>

          <!-- add activity -->
          <div>
            <button href="" id="addActivity" class="flex flex-row gap-2 mt-3">
              <h3>Add Activity</h3>
              <div
                class="flex justify-center bg-[#7993A0] w-6 py-1 rounded-full"
              >
                <span>
                  <svg
                    class="h-4 w-4"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M12 5V19M5 12H19"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </span>
              </div>
            </button>

            <div
              id="createActivity"
              class="fixed top-20 md:top-48 left-0 right-0 bottom-0 mx-auto w-full md:w-1/3 px-10 py-10 hidden"
            >
              <div class="bg-[#7993A0] p-6 rounded-lg">
                <form class="">
                  <h2 class="text-center pb-4 font-bold text-lg">
                    Create a new activity
                  </h2>

                  <div>
                    <label class="float-left" for="title">Title</label>
                    <input class="float-right w-1/3" type="text" name="title" />
                  </div>

                  <div class="pt-8">
                    <label class="float-left" for="date">Date</label>
                    <input class="float-right w-1/3" type="date" name="date" />
                  </div>

                  <div class="pt-8">
                    <label for="description">Description</label>
                    <br />
                    <textarea
                      class="w-full"
                      name="description"
                      cols="20"
                      rows="5"
                    ></textarea>
                  </div>

                  <div class="mb-4">
                    <label class="float-left" for="invite"
                      >Send an Invite</label
                    >
                    <div class="float-right">
                      <input type="text" name="invite" />
                      <button
                        class="bg-[#3E563E] text-white py-1 px-1 rounded-xl hover:bg-[#93A889]"
                      >
                        Send
                      </button>
                    </div>
                  </div>

                  <br />

                  <div class="flex justify-center items-center w-full pt-4">
                    <button
                      class="bg-[#3E563E] text-white py-2 px-4 rounded-xl hover:bg-[#93A889]"
                    >
                      Save
                    </button>
                  </div>
                </form>
              </div>
            </div>
          </div>
          <!-- add activity -->
        </div>
        <!-- Activities -->
      </div>
      <!-- left side -->

      <!-- right side -->
      <div>
        <!-- assigned items -->
        <div class="mt-0 md:mt-8 bg-[#A6907B] py-4 px-8 rounded-xl">
          <h1 class="font-bold text-xl">Assigned Items</h1>

          <lo class="marker:text-[#174140] marker:text-2xl text-xl">
            <li>Trip one</li>
            <li>Trip two</li>
          </lo>
        </div>
        <!-- assigned items -->

        <!-- activities completed -->
        <div class="mt-8 bg-[#A6907B] py-4 px-8 rounded-xl">
          <h1 class="font-bold text-xl">Activities Completed</h1>

          <lo class="marker:text-[#174140] marker:text-2xl text-xl">
            <li>Trip one</li>
            <li>Trip two</li>
          </lo>
        </div>
        <!-- activities completed -->
      </div>
      <!-- right side -->
    </div>
    <!-- main container -->
  </div>
</template>

<script setup>
import top from "../components/Top.vue"

// const add = document.querySelector("#add");
// const create = document.querySelector("#create");

// add.addEventListener("click", () => {
//   create.classList.toggle("hidden");
// });

// document.addEventListener("click", (event) => {
//   if (!add.contains(event.target) && !create.contains(event.target)) {
//     create.classList.add("hidden");
//   }
// });

// const addActivity = document.querySelector("#addActivity");
// const createActivity = document.querySelector("#createActivity");

// addActivity.addEventListener("click", () => {
//   createActivity.classList.toggle("hidden");
// });

// document.addEventListener("click", (event) => {
//   if (
//     !addActivity.contains(event.target) &&
//     !createActivity.contains(event.target)
//   ) {
//     createActivity.classList.add("hidden");
//   }
// });
</script>
