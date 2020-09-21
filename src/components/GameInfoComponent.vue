<template>
  <div class="container">
    <div class="game-info-1">
      <img class="game-info-image is-odd" :src="require('../assets/game_info_section/gangs.jpg')" />
      <div class="game-information">
        <h2>SOME HEADER TEXT</h2>
        <h3>SOME SUBTEXT</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nec urna ut dolor varius volutpat quis at dui. Nulla fringilla ultricies nulla ut accumsan. In sit amet felis at lectus lobortis fermentum efficitur id dolor. Suspendisse consectetur mauris at dolor dapibus accumsan ut id dui. Vestibulum tortor sapien, tempor id sapien ut, varius faucibus tellus. Praesent scelerisque enim leo, a semper tortor scelerisque sed. Etiam eu rhoncus mauris. In sodales quam vitae erat congue aliquet.</p>
      </div>
    </div>
    <div class="game-info-2">
      <div class="game-information">
        <h2>SOME HEADER TEXT</h2>
        <h3>SOME SUBTEXT</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nec urna ut dolor varius volutpat quis at dui. Nulla fringilla ultricies nulla ut accumsan. In sit amet felis at lectus lobortis fermentum efficitur id dolor. Suspendisse consectetur mauris at dolor dapibus accumsan ut id dui. Vestibulum tortor sapien, tempor id sapien ut, varius faucibus tellus. Praesent scelerisque enim leo, a semper tortor scelerisque sed. Etiam eu rhoncus mauris. In sodales quam vitae erat congue aliquet.</p>
      </div>
      <img class="game-info-image is-even" :src="require('../assets/game_info_section/sabotage.webp')" />
    </div>
    <div class="game-info-3">
      <img class="game-info-image is-odd" :src="require('../assets/game_info_section/cars.webp')" />
      <div class="game-information">
        <h2>SOME HEADER TEXT</h2>
        <h3>SOME SUBTEXT</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nec urna ut dolor varius volutpat quis at dui. Nulla fringilla ultricies nulla ut accumsan. In sit amet felis at lectus lobortis fermentum efficitur id dolor. Suspendisse consectetur mauris at dolor dapibus accumsan ut id dui. Vestibulum tortor sapien, tempor id sapien ut, varius faucibus tellus. Praesent scelerisque enim leo, a semper tortor scelerisque sed. Etiam eu rhoncus mauris. In sodales quam vitae erat congue aliquet.</p>
      </div>
    </div>
    <div class="game-info-4">
      <div class="game-information">
        <h2>SOME HEADER TEXT</h2>
        <h3>SOME SUBTEXT</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In nec urna ut dolor varius volutpat quis at dui. Nulla fringilla ultricies nulla ut accumsan. In sit amet felis at lectus lobortis fermentum efficitur id dolor. Suspendisse consectetur mauris at dolor dapibus accumsan ut id dui. Vestibulum tortor sapien, tempor id sapien ut, varius faucibus tellus. Praesent scelerisque enim leo, a semper tortor scelerisque sed. Etiam eu rhoncus mauris. In sodales quam vitae erat congue aliquet.</p>
      </div>
      <img class="game-info-image is-even" :src="require('../assets/game_info_section/customize.webp')" />
    </div>
  </div>
</template>

<script>
export default {
  name: "GameInfoComponent",
  data() {
    return {
      observer: null,
    };
  },
  mounted() {
    this.observer = new IntersectionObserver(
      (entries) => {
        this.handleIntersect(entries[0]);
      },
      { root: null, threshold: 0.5 }
    );

    document
      .getElementsByClassName("game-info-image")
      .forEach((x) => this.observer.observe(x));
  },
  destroyed() {
    this.observer.disconnect();
  },
  methods: {
    handleIntersect(entry) {
      if (entry.isIntersecting) {
        if (entry.target.classList.contains("is-odd")) {
          entry.target.classList.add("fade-in-to-right");
        } else {
          entry.target.classList.add("fade-in-to-left");
        }
        this.observer.unobserve(entry.target);
      }
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  margin-top: 40px;
  img {
    @media only screen and (max-width: 768px) {
      width: 100vw;
    }
    @media only screen and (min-width: 769px) {
      max-width: 900px;
    }
  }
  .game-information {
    max-width: 500px;
  }
}

.game-info-1,
.game-info-3 {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-bottom: 40px;

  @media only screen and (max-width: 768px) {
    flex-direction: column;
  }
  @media only screen and (min-width: 769px) {
    flex-direction: row;
  }
}

.game-info-2,
.game-info-4 {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-bottom: 40px;

  @media only screen and (max-width: 768px) {
    flex-direction: column-reverse;
  }
  @media only screen and (min-width: 769px) {
    flex-direction: row;
  }
}

/* Animations related CSS below */

.game-info-image {
  opacity: 0;
}

.is-odd {
  transform: translate(-20px, 0);
}

.is-even {
  transform: translate(20px, 0);
}

.fade-in-to-right {
  animation: fadeInToRight ease 1s forwards;
}

.fade-in-to-left {
  animation: fadeInToLeft ease 1s forwards;
}

@keyframes fadeInToRight {
  0% {
    opacity: 0;
    transform: translate(-20px, 0);
  }
  100% {
    opacity: 1;
    transform: translate(0px, 0);
  }
}

@keyframes fadeInToLeft {
  0% {
    opacity: 0;
    transform: translate(20px, 0);
  }
  100% {
    opacity: 1;
    transform: translate(0px, 0);
  }
}
</style>
