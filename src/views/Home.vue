<template>
  <div class="home">
    <HeroComponent />
    <SubheaderComponent />
    <LegionGridComponent />
  </div>
</template>

<script>
import HeroComponent from "../components/HeroComponent";
import SubheaderComponent from "../components/SubheaderComponent";
import LegionGridComponent from "../components/LegionGridComponent";

export default {
  name: "Home",
  components: {
    HeroComponent,
    SubheaderComponent,
    LegionGridComponent,
  },
};
</script>

<style scoped>
</style>