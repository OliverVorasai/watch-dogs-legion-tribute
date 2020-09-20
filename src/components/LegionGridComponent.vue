<template>
  <div>
    <div class="container">
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_1x1.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_1x2.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_1x3.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_1x4.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_1x5.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_2x1.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_2x2.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_2x3.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_2x4.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_2x5.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_3x1.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_3x2.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_3x3.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_3x4.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_3x5.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_4x1.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_4x2.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_4x3.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_4x4.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_4x5.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_5x1.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_5x2.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_5x3.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_5x4.png')" />
      <img class="legions" :src="require('../assets/grid_shots/watchdogs_5x5.png')" />
    </div>
    <img id="skull-flash" :src="require('../assets/watchdogs-legion-logo.svg')" />
  </div>
</template>

<script>
export default {
  name: "LegionGridComponent",
  methods: {
    sleep(ms) {
      return new Promise((resolve) => setTimeout(resolve, ms));
    },
    async animateSkull() {
      let legions = document.getElementsByClassName("legions");
      let skull = document.getElementById("skull-flash");

      // eslint-disable-next-line no-constant-condition
      while (true) {
        let target = legions[Math.floor(Math.random() * legions.length)];

        skull.style.height = target.height / 2 + "px";
        skull.style.width = target.width / 2 + "px";

        skull.style.top = target.offsetTop + (target.height/4) + "px";
        skull.style.left = target.offsetLeft + (target.width/4) + "px";

        await this.sleep(1000);

        let i = 0;
        while (i < 2) {
          skull.style.opacity = "1";
          await this.sleep(250);
          skull.style.opacity = "0";
          await this.sleep(250);
          skull.style.opacity = "1";
          await this.sleep(250);
          i += 1;
        }
        await this.sleep(1000);
      }
    },
  },
  mounted() {
    this.animateSkull();
  },
};
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  margin-top: 20px;
}

img {
  height: auto;
  width: 100%;
}

#skull-flash {
  position: absolute;
  opacity: 0;
  top: 0;
  left: 0;
  width: 50px;
  height: 50px;
  transition: 0.25s;
  filter: invert(100%);
}
</style>