<template>
     <header>
        <div class="container">
            <div class="row">
                <div class="col-lg-12">
                    <img class="img-responsive" width=200  src="./assets/profile-pic.png" alt="">
                    <div class="intro-text">
                        <span class="name">Vagner Da Silva</span>
                        <hr class="star-light">
                        <span class="skills">Sou um Desenvolvedor Web desde 2019 quando apliquei meu primeiro estágio</span>
                    </div>
                </div>
            </div>
        </div>
    </header>
    <section style="padding: 60px;">
        <div>Criação de portifolio</div>
    </section>
</template>

<style scoped>
.img-centered {
  margin: 0 auto;
}
header {
  text-align: center;
  background: #2e5d54;
  color: white;
}
header .container {
  padding-top: 100px;
  padding-bottom: 50px;
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
</style>