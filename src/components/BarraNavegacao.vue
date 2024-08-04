<template>

  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Navbar</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Features</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Pricing</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>

</template>
<script>


export default {
  components: {

  },

  data() {
    return {
      isMenuOpen: false
    }
  },
  computed: {
    classMenuDeslogado() {
      if (this.isMenuOpen) { return 'show' }
      return 'collapse navbar-collapse justify-content-end'
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {

    closeMenu() {
      this.isMenuOpen = false
    },

    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },

    efetuarLogout() {
      localStorage.removeItem('token')
    },
    handleScroll() {
      this.hasScrolled = window.scrollY > 0
      const navbar = document.querySelector('.navbar')
      if (this.hasScrolled) {
        navbar.classList.add('scrolled')
      } else {
        navbar.classList.remove('scrolled')
      }
    }
  }
}
</script>

<style>
.navbar {
  /*background: #7FD6F6;*/
  background: transparent;
  transition: background-color 0.3s;
  color: white;
}

.navbar.scrolled {
  background: white;
}

.show {
  justify-content: start;
  text-align: justify;
  /* //border: 1px dashed black; */
  margin-left: 5px;
  padding: 1px;
  color: black;
  width: 100%;
}

body {
  background-color: rgb(248, 248, 248);
}
</style>
