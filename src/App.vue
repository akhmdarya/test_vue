<template>
  <navbar-component/>
  <div class="app">

    <router-view/>

  </div>
</template>

<script>
import NavbarComponent from "@/components/NavbarComponent";
export default {
  components: {NavbarComponent}
}
</script>

<style >
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>
