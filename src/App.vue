<template>
	<div id="app">
		<Main />
	</div>
</template>

<script>
import Main from "./components/Main.vue";

export default {
  name: "app",
  components: {
    Main,
  },
};
</script>

<style>
@font-face {
  font-family: "FuturaNo2D";
  src: url("~/assets/fonts/FuturaNo2D-DemiBold.woff");
}

#app {
  font-weight: 600;
  text-transform: uppercase;
  font-family: "FuturaNo2D", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 2em 0em;
  width: 50vw;
}

button {
  font-weight: 700;
  text-transform: uppercase;
  font-family: "FuturaNo2D", Helvetica, Arial, sans-serif;
  color: white;
  transition: all 200ms;
  background-color: #ff9c00;
  border: none;
  border-radius: 2px;
  vertical-align: middle;
  padding: 6px 1em;
  font-size: 2.5em;
  border-radius: 5px;
}
</style>
