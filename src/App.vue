<template>
  <div id="app">
    <MaskedInput wrap="XX/XX/XXXX" />
    <MaskedInput wrap="+1 (XXX) - XXX - XXXX" />
  </div>
</template>

<script>
import MaskedInput from "@/components/MaskedInput";
export default {
  name: "App",
  components: { MaskedInput }
};
</script>

<style lang="css">
body {
  background-color: lightslategrey;
  color: white;
  font-size: 40px;
}
input {
  font-size: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
