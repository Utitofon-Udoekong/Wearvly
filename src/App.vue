<template>
  <div :class="isDay ? 'day' : 'night'">
    <!-- ................ sunny weather ..................-->
    <section class="col-md-12 header1" v-if="clearSky">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div class>
            <!-- logo -->
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityfound">
              <!-- low-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- high-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityfound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <!-- city -->
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>Bright day ahead</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <div class="weatherSearch my-4">
                <!-- city-search -->
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class>{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- ends -->
    <!-- ................ snowy ..................-->
    <section class="header2" v-if="snowy">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div class>
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityfound">
              <!-- min-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- max-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityfound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>Theres {{weather.description}} falling</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <div class="weatherSearch my-4">
                <!-- city search -->
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class>{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- ends -->
    <!-- ................ stormy ..................-->

    <section class="header3" v-if="stormy">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div class>
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityfound">
              <!-- min-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- max-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityfound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>Its stormy out there</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <div class="weatherSearch my-4">
                <!-- city-search -->
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class>{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- ends -->
    <!-- ................ cloudy ..................-->

    <section class="header4" v-if="cloudy">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div class>
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityfound">
              <!-- min-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- max-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityfound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>Cloudy weather ahead</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <div class="weatherSearch my-4">
                <!-- city-search -->
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class>{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- ends -->
    <!-- ................night ..................-->

    <section class="header5" v-if="clearNight">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div>
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityFound">
              <!-- min-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- max-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityFound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>pleasant night</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <!-- citysearch -->
              <div class="weatherSearch my-4">
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class="cities">{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- ends -->
    <!-- ...................rain ...............-->

    <section class="header6" v-if="rainy">
      <div class="row no-gutters">
        <div class="col-md-8 weather-page">
          <div class>
            <div class="logo">Wearvly</div>
            <div class="averages" v-if="!cityfound">
              <!-- min-temp -->
              <p>
                <img src="./assets/down.svg" alt />
                {{ weather.lowTemp }}&deg;C
              </p>
              <p>Feels Like: {{weather.feelsLike}}&deg;C</p>
              <!-- max-temp -->
              <p>
                <img src="./assets/up.svg" alt />
                {{ weather.highTemp }}&deg;C
              </p>
            </div>
            <div class="temperal-info" v-if="!cityfound">
              <!-- main-temp -->
              <h1>{{ weather.temperature }}&deg;C</h1>
              <div class="location">
                <h2>{{ weather.cityName }}</h2>
                <p>06:09 - Sunday, 6 Oct 2020</p>
              </div>
              <div class="weather-gif">
                <img src alt />
                <p>Its raining out there</p>
              </div>
            </div>
          </div>
        </div>
        <div class="weather-info-page col-md-4">
          <div class="row">
            <div class="container">
              <div class="weatherSearch my-4">
                <!-- city-search -->
                <form v-on:submit.prevent="getWeather">
                  <input
                    type="search"
                    placeholder="search a city"
                    v-model="citySearch"
                    autocomplete="off"
                  />
                  <p class="text-center my-3" v-if="cityFound">No city found</p>
                </form>
              </div>
              <div class="searchedCities">
                <a class>{{ weather.country }}</a>
                <a class>Sealevel: {{weather.sealevel}}m</a>
                <a class>Ground-level: {{weather.groundlevel}}m</a>
              </div>
            </div>
            <div class="container mt-5">
              <!-- weather-details -->
              <div class="weather-details py-5">
                <h2 class="pb-3">Weather Details</h2>
                <div class="details">
                  <p>Cloudy</p>
                  <p>{{weather.clouds}}%</p>
                </div>
                <div class="details">
                  <p>Humidity</p>
                  <p>{{ weather.humidity }}%</p>
                </div>
                <div class="details">
                  <p>Wind speed</p>
                  <p>{{ weather.windSpeed }}km/h</p>
                </div>
                <div class="details">
                  <p>Weather Description</p>
                  <p>{{weather.description}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cityFound: false,
      stormy: false,
      cloudy: false,
      clearSky: false,
      clearNight: true,
      snowy: false,
      rainy: false,

      isDay: true,
      citySearch: "",
      weather: {
        cityName: "Gwarinpa",
        country: "NG",
        temperature: 12,
        description: "Clouds everywhere",
        lowTemp: "19",
        highTemp: "30",
        feelsLike: "20",
        humidity: "55",
        windSpeed: "2",
        clouds: "92",
        sealevel: "1024",
        groundlevel: "324"
      }
    };
  },
  methods: {
    getWeather: async function() {
      console.log(this.citySearch);
      const key = "5299e83c9cf2fef510fb8ddaa3206ac8";
      const baseURL = `http://api.openweathermap.org/data/2.5/weather?q=${this.citySearch}&appid=${key}&units=metric`;

      //fetch weatherx
      try {
        const response = await fetch(baseURL);
        const data = await response.json();
        console.log(data);
        this.citySearch = "";
        this.weather.cityName = data.name;
        this.weather.country = data.sys.country;
        this.weather.temperature = Math.round(data.main.temp);
        this.weather.description = data.weather[0].description;
        this.weather.lowTemp = Math.round(data.main.temp_min);
        this.weather.highTemp = Math.round(data.main.temp_max);
        this.weather.feelsLike = Math.round(data.main.feels_like);
        this.weather.humidity = Math.round(data.main.humidity);
        this.weather.windSpeed = Math.round(data.wind.speed);
        this.weather.clouds = data.clouds.all;
        this.weather.sealevel = Math.round(data.main.sea_level);
        this.weather.groundlevel = Math.round(data.main.grnd_level);

        const timeOfDay = data.weather[0].icon;

        ///check for time of day
        if (timeOfDay.includes("n")) {
          this.isDay = false;
        } else {
          this.isDay = true;
        }

        const mainWeather = data.weather[0].main;
        //check weather animations
        if (mainWeather.includes("Clouds")) {
          this.stormy = false;
          this.cloudy = true;
          this.clearSky = false;
          this.clearNight = false;
          this.snowy = false;
          this.rainy = false;
        }
        if (mainWeather.includes("Thunderstorm")) {
          this.stormy = true;
          this.cloudy = false;
          this.clearSky = false;
          this.clearNight = false;
          this.snowy = false;
          this.rainy = false;
        }
        if (mainWeather.includes("Rain")) {
          this.stormy = true;
          this.cloudy = false;
          this.clearSky = false;
          this.clearNight = false;
          this.snowy = false;
          this.rainy = true;
        }
        if (mainWeather.includes("Clear") && this.isDay) {
          this.stormy = false;
          this.cloudy = false;
          this.clearSky = true;
          this.clearNight = false;
          this.snowy = false;
          this.rainy = false;
        }
        if (mainWeather.includes("Clouds") && !this.isDay) {
          this.stormy = false;
          this.cloudy = false;
          this.clearSky = false;
          this.clearNight = true;
          this.snowy = false;
          this.rainy = false;
        }
        if (mainWeather.includes("Snow")) {
          this.stormy = false;
          this.cloudy = false;
          this.clearSky = false;
          this.clearNight = false;
          this.snowy = true;
          this.rainy = false;
        }

        this.cityFound = false;
      } catch (error) {
        console.log(error);
        this.cityFound = true;
      }
    }
  }
};
</script>

<style scoped>
@import "./assets/styles.css";
</style>
