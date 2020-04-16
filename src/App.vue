<template>
  <div
    id="app"
    :class="
      typeof weather.main != 'undefined' && weather.main.temp > 16 ? 'warm' : ''
    "
  >
    <meta http-equiv="refresh" content="20" />
    <main>
      <div class="Attention">
        <p>Figyelem a kereső csak létező városokra add eredményt!</p>
      </div>
      <div class="search-box">
        <input
          type="text"
          class="search-bar"
          placeholder="Keresett város..."
          v-model="query"
          @keypress="fetchWeather"
        />
      </div>

      <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
        <div class="location-box">
          <div class="location">{{ weather.name }}, {{ weather.sys.country }}</div>
        </div>

        <div class="weather-box">
          <div class="temp">{{ Math.round(weather.main.temp) }}°c</div>
          <div class="weather">{{ weather.weather[0].main }}</div>
          <div class="hi_low"></div>
          <div class="image"></div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      api_key: "a0fa377f6275791c424358916f1fd569",
      url_base: "https://api.openweathermap.org/data/2.5/",
      query: "",
      weather: {},
      icon: ""
    };
  },

  methods: {
    fetchWeather(e) {
      if (e.key == "Enter") {
        fetch(
          `${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`
        )
          .then(res => {
            return res.json();
          })
          .then(this.setResults);
      }
    },
    setResults(results) {
      this.weather = results;
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
p {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}
body {
  font-family: "montserrat", sans-serif;
<<<<<<< HEAD
  background-image: linear-gradient(purple, blue);
  display: flex;
  justify-content: center;
=======
    background-image: linear-gradient(
    purple,blue
  );
  display:flex;
 justify-content: center
>>>>>>> 2c07b26c1da37606c60d8b03a3bd6de1db2850be
}
main {
  min-height: 100vh;
  padding: 25px;
<<<<<<< HEAD
  width: 30vw;
=======
  width:30vw;


>>>>>>> 2c07b26c1da37606c60d8b03a3bd6de1db2850be
}
#app {
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}
.search-box {
  width: 100%;
  margin-bottom: 30px;
}
.search-box .search-bar {
  display: block;
  width: 100%;
  padding: 15px;
  color: black;
  font-size: 20px;
  appearance: none;
  outline: none;
  background: none;
<<<<<<< HEAD
  border-style: none;
  background-color: rgba(255, 255, 255, 0.4);
=======
  border-style:none;
  background-color: rgba(255,255,255,0.4);
>>>>>>> 2c07b26c1da37606c60d8b03a3bd6de1db2850be
  border-radius: 20px;
  transition: 0.4s;
}
.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 20px;
}
.location-box .location {
  color: #fff;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}
.location-box .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}
.weather-box {
  text-align: center;
}
.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0px;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.weather-box .weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
}
</style>