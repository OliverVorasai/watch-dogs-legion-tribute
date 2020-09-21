<template>
  <div class="home">
    <HeroComponent />
    <SubheaderComponent />
    <LegionGridComponent />
    <GameInfoComponent />
  </div>
</template>

<script>
import HeroComponent from "../components/HeroComponent";
import SubheaderComponent from "../components/SubheaderComponent";
import LegionGridComponent from "../components/LegionGridComponent";
import GameInfoComponent from "../components/GameInfoComponent";

export default {
  name: "Home",
  components: {
    HeroComponent,
    SubheaderComponent,
    LegionGridComponent,
    GameInfoComponent,
  },
};
</script>

<style scoped>
</style>