<template>
  <div class="home">
    <HeroComponent />
    <SubheaderComponent />
    <LegionGridComponent />
  </div>
</template>

<script>
import LegionGridComponent from "../components/LegionGridComponent";
import HeroComponent from "../components/HeroComponent";
import SubheaderComponent from "../components/SubheaderComponent";

export default {
  name: 'Home',
  components: {
    LegionGridComponent,
    HeroComponent,
    SubheaderComponent,
  }
}
</script>

<style scoped>
</style>