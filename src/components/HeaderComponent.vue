<template>
  
  <div class="text">Когнитивные искажения</div>
  <img src="../assets/irrigation.png" />
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {};
  },
};
</script>

<style scoped>
.text {
  padding-top: 18px;
  padding-bottom: 18px;
  background: #fff;
  width: 334px;
  border-radius: 30px;
  margin-top: 60px;
  color: #297d77;
  font-size: 36px;
  font-weight: 600;
  text-transform: uppercase;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}

img {
  width: 53px;
  position: absolute;
  left: calc(50% - 26.5px + 167px - 26px + 8px);
  top: calc(60px - 18px);
}
</style>
