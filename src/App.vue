<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>
<style lang="scss">
.show_down {
  box-shadow: 0 2px 12px 0 rgb(0 0 0 / 10%);
}
.marpad{
  margin: 12px;
  padding: 12px;
}
</style>