<template>
  <!-- body div -->
  <div class="mx-8 my-8">
    
    <div>
      <top></top>
    </div>

    <!-- main -->
    <div class="w-full h-screen pt-14 sm:pt-16">
      <!-- sidebar -->
      <div class="float-left w-full sm:w-1/4 pr-0 sm:pr-10">
        <!-- weather -->
        <div class="bg-[#CED9DF] mb-4 px-4 py-4 rounded-xl">
          <h1 class="text-sm sm:text-xl font-bold">Weather</h1>

          <div id="weather" class="text-sm sm:text-xl"></div>
        </div>
        <!-- weather -->

        <!-- ferry -->
        <div class="bg-[#CED9DF] mb-4 px-4 py-4 rounded-xl">
          <h1 class="text-sm sm:text-xl font-bold">Ferry Schedule</h1>
        </div>
        <!-- ferry -->
      </div>
      <!-- sidebar -->

      <!-- content -->
      <div class="float-right w-full sm:w-3/4">
        <!-- image and buttons -->
        <div>
          <div>
            <img
              class="absolute rounded-xl h-40 sm:h-96 w-[90%] sm:w-[73%]"
              src="../assets/camp.jpg"
              alt="camping site"
            />
          </div>

          <!-- buttons -->
          <div>
            <a
              class="relative float-left bg-[#174140] text-white text-sm sm:text-lg text-center w-[20%] mt-36 sm:mt-[23rem] ml-[28%] sm:ml-[28%] py-1 hover:bg-[#93A889]"
              href="/trips"
            >
              <h2>Trips</h2>
            </a>

            <a
              class="relative float-right bg-[#174140] text-white text-sm sm:text-lg text-center w-[25%] sm:w-[20%] mt-36 sm:mt-[23rem] mr-[20%] sm:mr-[27%] py-1 hover:bg-[#93A889]"
              href="/lists"
            >
              <h2>Activities/List</h2>
            </a>
          </div>
          <!-- buttons -->
        </div>
        <!-- image and buttons -->

        <!-- main content -->
        <div class="clear-both pt-4 sm:pt-8 flex justify-center gap-2 sm:gap-4">
          <!-- side 1 -->
          <div
            class="clear-both float-none sm:float-left bg-[#D9D9D9] w-full sm:w-[45%] ml-2 sm:ml-4 py-4 rounded-md"
          >
            <h1 class="text-center font-bold text-xl">Trips</h1>
          </div>
          <!-- side 1 -->

          <!-- side 2 -->
          <div
            class="clear-both float-none sm:float-right bg-[#D9D9D9] w-full sm:w-[45%] ml-2 sm:ml-4 py-4 rounded-md"
          >
            <h1 class="text-center font-bold text-xl">To Bring</h1>
          </div>
          <!-- side 2 -->
        </div>
        <!-- main content -->
      </div>
      <!-- content -->
    </div>
    <!-- main -->
  </div>
  <!-- body div -->
</template>


<script setup>
import top from "../components/Top.vue"

const API_KEY = "210bdd68e667e27d82460fb312527f36";

const url = `https://api.openweathermap.org/data/2.5/forecast?q=Nanaimo,CA&units=metric&cnt=4&appid=${API_KEY}`;
fetch(url)
  .then((response) => response.json())
  .then((data) => {
    const forecasts = data.list;

    const forecastList = document.getElementById("weather");
    forecasts.forEach((forecast) => {
      const date = new Date(forecast.dt * 1000).toLocaleString("en-US", {
        weekday: "long",
      });
      const description = forecast.weather[0].description;
      const temperature = Math.round(forecast.main.temp);
      const listItem = document.createElement("p");
      listItem.textContent = `${date} ${description} ${temperature}°C`;
      forecastList.appendChild(listItem);
    });
  })
  .catch((error) => console.error(error));

</script>
