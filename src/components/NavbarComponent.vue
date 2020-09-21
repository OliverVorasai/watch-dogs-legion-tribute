<template>
  <nav class="navbar">
    <div class="navbar-items">
      <div class="navbar-left">
        <img :src="require('../assets/watch_dogs_legion_logo.webp')" />
      </div>
      <div class="navbar-right">
        <div class="pre-order">
          <p>PRE-ORDER</p>
          <p>10.29.2020</p>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavbarComponent",
};
</script>

<style scoped lang="scss">
nav {
  width: 100%;
  @media only screen and (max-width: 768px) {
    height: 70px;
  }
  @media only screen and (min-width: 769px) {
    height: 100px;
  }
  position: fixed;
  top: 0;
  background-color: rgba(25, 25, 25, 0.8);
  z-index: 99;
  overflow: hidden;

  .navbar-items {
    width: 100%;
    height: 100%;
    position: relative;

    .navbar-left {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      img {
        @media only screen and (max-width: 768px) {
          max-height: 40px;
        }
        margin-left: 20px;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
      }
    }
    .navbar-right {
      position: absolute;
      top: 0;
      right: 0;
      height: 100%;
      width: 200px;
      background-color: red;
      p {
        margin: 0;
        @media only screen and (max-width: 768px) {
          font-size: 1em;
        }
        @media only screen and (min-width: 769px) {
          font-size: 1.25em;
        }
      }
      .pre-order {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 100%;
      }
    }
  }
}
</style>