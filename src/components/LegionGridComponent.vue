<template>
  <div>
    <div class="container">
      <div class="grid-container">
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
        <img id="skull-flash" :src="require('../assets/watch-dogs-legion-logo.svg')" />
      </div>
      <div class="play-info">
        <h2>
          PLAY AS
          <span class="glitch-text" data-text="ANYONE">ANYONE</span>
        </h2>
        <h3>ANYONE CAN BE YOUR WEAPON</h3>
        <p>Each character has their own backstory, personality, and skill set—all of which comes into play as you personalize your team. Swap between characters as you explore an open world online with friends. Enjoy free updates of new modes, rewards, and themed events.</p>
      </div>
    </div>
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

        skull.style.top = target.offsetTop + target.height / 4 + "px";
        skull.style.left = target.offsetLeft + target.width / 4 + "px";

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

<style scoped lang="scss">
@use "../mixins.scss";
@include mixins.glitchy-text;

.container {
  margin-top: 20px;
  position: relative;
}
.grid-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
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

.play-info {
  max-width: 450px;
  max-height: 600px;
  padding: 50px;
  position: absolute;
  top: 20%;
  right: 20%;
  background: rgba(25, 25, 25, 0.9);

  h2 {
    @media only screen and (max-width: 768px) {
      font-size: 2em;
    }
    @media only screen and (min-width: 769px) {
      font-size: 3em;
    }
    margin: 20px 0;
  }
  h3 {
    @media only screen and (max-width: 768px) {
      font-size: 1em;
    }
    @media only screen and (min-width: 769px) {
      font-size: 2em;
    }
    color: red;
    margin: 20px 0;
  }

  @media only screen and (max-width: 768px) {
    position: relative;
    top: 0;
    right: 0;
    margin: 0 auto;
    background: black;
  }
  @media only screen and (min-width: 769px) {
  }
}
</style>