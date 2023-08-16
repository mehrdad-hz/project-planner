<template>
  <div class="container">
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  components: { Navbar },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:wght@300;400;500;700&display=swap");

* {
  margin: 0;
  padding: 0;
  transition: all 300ms;
  box-sizing: border-box;
  font-family: "Ubuntu", sans-serif;
}
body {
  background: #0a192f;
  color: #eee;
}

.container {
  max-width: 700px;
  margin: auto;
}

@media screen and (max-width: 768px) {
  .container {
    margin: 0 10px;
  }
}
</style>
