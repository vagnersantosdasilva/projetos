<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <img class="img-responsive" width=200 src="./assets/profile-pic.png" alt="">

          <div class="intro-text">

            <span class="name">Vagner Da Silva</span>
            <hr class="star-light">

            <div style="display: inline-flex;" class="mt-4">
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"
                alt="JavaScript" />
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" />
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java" />
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" alt="Spring Boot" />
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" alt="Vue.js" />
              <img width="30" height="30"
                src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React.js" />
            </div>

          </div>
        </div>
      </div>
    </div>
  </header>
  <section style="padding: 60px;">

    <div class="container">
      <span class="title">Minha trajetória</span>
      <hr class="mb-4">
      <div class="timeline">
        <div class="timeline-container" ref="timelineContainer">
          <div class="timeline-item" v-for="event in events" :key="event.year" :data-content="event.description">
            <span>{{ event.year }}</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      events: [
        { year: 2019, description: 'Comecei meu primeiro estágio como Desenvolvedor Web.' },
        { year: 2020, description: 'Trabalhei em projetos importantes e aprendi novas tecnologias.' },
        { year: 2021, description: 'Fui promovido a Desenvolvedor Júnior.' },
        { year: 2022, description: 'Concluí vários cursos e obtive certificações.' },
        { year: 2023, description: 'Atualmente trabalhando como Desenvolvedor Pleno.' },
      ]
    }
  },
  mounted() {
    this.addTooltipEffects();
  },
  methods: {
    addTooltipEffects() {
      this.$nextTick(() => {
        this.$refs.timelineContainer.querySelectorAll('.timeline-item').forEach(item => {
          item.addEventListener('mouseenter', (e) => {
            const tooltip = document.createElement('div');
            tooltip.className = 'tooltip';
            tooltip.innerText = item.getAttribute('data-content');
            item.appendChild(tooltip);
            tooltip.style.display = 'block';
          });

          item.addEventListener('mouseleave', (e) => {
            const tooltip = item.querySelector('.tooltip');
            if (tooltip) {
              tooltip.remove();
            }
          });
        });
      });
    }
  }
}
</script>

<style scoped>
.img-centered {
  margin: 0 auto;
}

header {
  text-align: center;
  /* background: #2e5d54; */
  background: rgb(235, 236, 254);
  /* color: white; */
  /*color:rgb(123, 109, 181);*/
  color: rgb(103, 91, 150);
}

header .container {
  padding-top: 100px;
  padding-bottom: 50px;
  height: calc(100vh - 10vh);
}

header img {
  display: block;
  margin: 0 auto 20px;
}

header .intro-text .name {
  display: block;
  font-family: "Montserrat", "Helvetica Neue", Helvetica, Arial, sans-serif;
  text-transform: uppercase;
  font-weight: 700;
  font-size: 2em;
}

header .intro-text .skills {
  font-size: 1.25em;
  font-weight: 300;
}

hr {
  width: 220px;
  font-weight: 700;
  color: rgb(103, 91, 150);
  border: none;
  border-top: 5px solid rgb(76, 64, 127);
  margin: 0 auto;

}

.title {
  display: flex;
  justify-content: center;
  color: rgb(103, 91, 150);
  font-family: "Montserrat", "Helvetica Neue", Helvetica, Arial, sans-serif;
  text-transform: uppercase;
  font-weight: 700;
  font-size: 2em;
}

.timeline {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 40px 0;
  position: relative;
}

.timeline-container {
  display: flex;
  justify-content: space-between;
  width: 80%;
  position: relative;
}

.timeline-container::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  height: 4px;
  background: #ddd;
  z-index: 1;
}

.timeline-item {
  position: relative;
  z-index: 2;
  cursor: pointer;
}

.timeline-item span {
  display: block;
  position: absolute;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  background: #fff;
  padding: 5px 10px;
  border-radius: 4px;
  border: 1px solid #ddd;
}

.timeline-item::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 20px;
  height: 20px;
  background: #fff;
  border: 4px solid #666;
  border-radius: 50%;
  box-shadow: 0 0 0 3px #ddd;
  z-index: 3;
}

.tooltip {
  position: absolute;
  top: -60px;
  left: 50%;
  transform: translateX(-50%);
  background: #333;
  color: #fff;
  padding: 10px;
  border-radius: 5px;
  white-space: nowrap;
  display: none;
  z-index: 4;
}
</style>