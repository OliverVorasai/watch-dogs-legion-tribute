<template>
  <div class="home">
    <NavbarComponent />
    <HeroComponent />
    <SubheaderComponent />
    <LegionGridComponent />
    <GameInfoComponent />
    <FooterComponent />
  </div>
</template>

<script>
import NavbarComponent from "../components/NavbarComponent";
import HeroComponent from "../components/HeroComponent";
import SubheaderComponent from "../components/SubheaderComponent";
import LegionGridComponent from "../components/LegionGridComponent";
import GameInfoComponent from "../components/GameInfoComponent";
import FooterComponent from "../components/FooterComponent";

export default {
  name: "Home",
  components: {
    NavbarComponent,
    HeroComponent,
    SubheaderComponent,
    LegionGridComponent,
    GameInfoComponent,
    FooterComponent,
  },
};
</script>

<style scoped>
</style>