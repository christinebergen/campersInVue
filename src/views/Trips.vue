<template>
    <div class="mx-8 my-8">
  
      <div>
        <top></top>
      </div>
  
      <!-- all trips -->
      <div class="clear-both w-full h-screen pt-8 gap-10">
        <!-- current trips -->
        <div class="float-left w-full sm:w-2/3">
          <div class="bg-[#D9D9D9] px-10 py-8 rounded-xl mb-6">
            <!-- sort by -->
            <div class="relative">
              <a
                class="rounded-lg text-left font-medium focus:outline-none focus:shadow-outline-blue transition ease-in-out duration-150"
                id="sort"
              >
                <h3 class="float-right hover:scale-75 transition-all">Sort By</h3>
              </a>
  
              <div
                class="mt-6 origin-top-right absolute right-0 z-10 w-56 rounded-md shadow-lg hidden"
              >
                <div class="rounded-md bg-[#7993A0] shadow-xs">
                  <div class="py-1">
                    <a
                      href=""
                      class="block px-4 py-2 text-md text-white hover:bg-[#CED9DF]"
                      >Soonest</a
                    >
                    <a
                      href="#"
                      class="block px-4 py-2 text-md text-white hover:bg-[#CED9DF]"
                      >Furthest</a
                    >
                  </div>
                </div>
              </div>
            </div>
  
            <!-- sort by -->
  
            <h1 class="text-xl font-bold">Current Trips</h1>
  
            <span id="dispalytrip"></span>
  
            <!-- trip -->
            <div class="">
              <lo class="marker:text-[#174140] marker:text-2xl text-xl">
                <li id="trip"></li>
              </lo>
            </div>
            <!-- trip -->
  
            <!-- create new trip -->
            <div class="pt-8">
              <!-- add trip -->
              <div>
                <button href="" id="add" class="flex flex-row gap-2">
                  <h3>Create a new trip</h3>
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
                    <form>
                      <h2 class="text-center pb-4 font-bold text-lg">
                        Create a new trip
                      </h2>
  
                      <div>
                        <label class="float-left" for="title">Location</label>
                        <input
                          class="float-right w-1/3"
                          type="text"
                          name="title"
                          id="location"
                          required
                        />
                      </div>
  
                      <div class="pt-8">
                        <label class="float-left" for="date">Start Date</label>
                        <input
                          class="float-right w-1/3"
                          type="date"
                          name="date"
                          id="startDate"
                          required
                        />
                      </div>
  
                      <div class="pt-8">
                        <label class="float-left" for="date">End Date</label>
                        <input
                          class="float-right w-1/3"
                          type="date"
                          name="date"
                          id="endDate"
                          required
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
                          id="description"
                        ></textarea>
                      </div>
  
                      <div>
                        <label class="float-left" for="invite"
                          >Send an Invite</label
                        >
                        <div class="float-right">
                          <input type="text" name="invite" />
                        </div>
                      </div>
  
                      <br />
  
                      <div class="flex justify-center items-center w-full pt-4">
                        <button
                          class="bg-[#3E563E] text-white py-2 px-4 rounded-xl hover:bg-[#93A889]"
                          id="saveTrip"
                        >
                          Save
                        </button>
                      </div>
                    </form>
                  </div>
                </div>
              </div>
              <!-- add trip -->
            </div>
            <!-- create new trip -->
          </div>
        </div>
        <!-- current trips -->
  
        <!-- past trips -->
        <div class="float-right w-full sm:w-1/3 pl-0 sm:pl-10">
          <div class="bg-[#CED9DF] px-10 py-8 rounded-xl">
            <h1 class="text-xl font-bold">Past Trips</h1>
  
            <!-- past trip -->
            <div class="">
              <lo class="marker:text-[#174140] marker:text-2xl text-xl">
                <li id="pastTrip"></li>
              </lo>
            </div>
            <!-- past trip -->
          </div>
        </div>
        <!-- past trips -->
      </div>
      <!-- all trips -->
    </div>
  </template>
  
  <script setup>
  import top from "../components/Top.vue"
  
  // const sort = document.querySelector("#sort");
  // const menu = sort.nextElementSibling;
  
  // sort.addEventListener("click", () => {
  //   menu.classList.toggle("hidden");
  // });
  
  // document.addEventListener("click", (event) => {
  //   if (!sort.contains(event.target) && !menu.contains(event.target)) {
  //     menu.classList.add("hidden");
  //   }
  // });
  
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
  
  
  // let tripList = [];
  
  // function addTrip() {
  //   let trip = {
  //     location: document.querySelector("#location").value,
  //     startDate: document.querySelector("#startDate").value,
  //     endDate: document.querySelector("#endDate").value,
  //     description: document.querySelector("#description").value,
  //   };
  //   tripList.push(trip);
  
  //   localStorage.setItem("location", String(trip.location));
  //   localStorage.setItem("startDate", String(trip.startDate));
  //   localStorage.setItem("endDate", String(trip.endDate));
  //   localStorage.setItem("description", String(trip.description));
  //   console.log("trip saved");
  // }
  
  // document.querySelector("#saveTrip").addEventListener("click", function () {
  //   addTrip();
  //   document.querySelector("#trip").innerHTML = JSON.stringify(tripList);
  // });
  
  // let location = localStorage.getItem("location");
  // document.querySelector("#displaytrip").innerHTML = location;
  
  // let currentDate = new Date();
  // tripList.forEach(function (trip) {
  //   let endDate = new Date(trip.endDate);
  //   if (endDate < currentDate) {
  //     document.querySelector("#pastTrip").innerHTML += JSON.stringify(trip);
  //   }
  // });
  </script>
  