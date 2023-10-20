<template>
  <div id="root">
    <header-component />
    <add-form />
  </div>
</template>

<script>
import AddForm from "@/components/AddForm.vue";
import HeaderComponent from "@/components/HeaderComponent.vue";
export default {
  name: "App",
  components: { AddForm, HeaderComponent },
  data() {
    return {};
  },
};
</script>

<style>
@font-face {
  font-family: myFont;
  src: url("./style/AlumniSans-Regular.ttf");
}
body {
  background-color: #a1d9b7;
  font-family: myFont;
}
option, select, button, input{
  font-family: myFont;
  font-size: 24px;
}
</style>
