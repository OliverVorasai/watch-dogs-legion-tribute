<template>
  <div class="container">
    <div class="left-image">
      <img :src="require('../assets/gold-skull.jpg')" />
    </div>

    <div class="right-text grid-container-right">
      <h2>
        WELCOME TO THE
        <span class="glitch-text" data-text="RESISTANCE">RESISTANCE</span>
      </h2>
      <h3>Build a Resistance to Fight Back.</h3>
      <p>London's facing its downfall courtesy of state surveillance, private military, and organized crime. Recruit a well-rounded resistance to overthrow the wankers ruining this once-great city. The fate of London lies with you.</p>
      <div class="iframe-container">
        <iframe
          class="responsive-iframe"
          src="https://www.youtube.com/embed/nGBrGqXILgM"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SubheaderComponent",
};
</script>

<style scoped lang="scss">
@use "../mixins.scss";
@include mixins.glitchy-text;

.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(0, 1fr));
  grid-template-rows: 1fr;
}

.left-image {
  grid-column: 1 / 3;
  @media only screen and (max-width: 1023px) {
    display: none;
  }
  img {
    width: auto;
    height: 100%;
  }
}

.right-text {
  grid-column: 3 / 6;
  h2 {
    @media only screen and (max-width: 768px) {
      font-size: 3em;
    }
    @media only screen and (min-width: 769px) {
      font-size: 4em;
    }
    margin: 20px 0;
  }
  h3 {
    @media only screen and (max-width: 768px) {
      font-size: 2em;
    }
    @media only screen and (min-width: 769px) {
      font-size: 3em;
    }
    color: red;
    margin: 20px 0;
  }
  p {
    max-width: 400px;
    margin: 0 auto;
    margin-bottom: 20px;
  }

  .iframe-container {
    position: relative;
    overflow: hidden;
    width: 100%;
    padding-top: 56.25%;
    .responsive-iframe {
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      width: 100%;
      height: 100%;
    }
  }
}

</style>