<template>
  <div id="app">
    <header>
      <div :class="menuClass" @click="changeMenu">
        <div class="bar half start"></div>
        <div class="bar"></div>
        <div class="bar half end"></div>
      </div>      
      <nav :class="navClass">
        <ul class="nav-list">
          <li>
            <a href="#about" class="nav-link" @click="changeMenu">About me</a>
          </li>
          <li>
            <a href="#skills" class="nav-link" @click="changeMenu">Skills</a>
          </li>
          <li>
            <a href="#experience" class="nav-link" @click="changeMenu">Experience</a>
          </li>
          <li>
            <a href="#projects" class="nav-link" @click="changeMenu">Projects</a>
          </li>
          <li>
            <a href="#awards" class="nav-link" @click="changeMenu">Awards</a>
          </li>
        </ul>
      </nav>
        <div class="landing-text">
          <h1 data-aos='fade-in' data-aos-delay='300'>Gabriel Lemos Rodrigues</h1>
          <h6 data-aos='fade-in' data-aos-delay='400'>Computer Science student at Western University</h6>
          <div class="icons" data-aos='fade-in' data-aos-delay='400'>
            <a href="https://github.com/Lemos00">
              <img src="./assets/images/icons/github-icon.png" alt="github icon" class="landing-icons">
            </a>
            <a href="https://www.linkedin.com/public-profile/in/gabriel-lemos-rodrigues-b96824198/?challengeId=AQH6iKldX2AKxgAAAXQrU-akdhO21UuzJYHrvwhQmlr3ScLKtzJsheZwfs7osibLRbauv6bXa0vLfy9Pdw9T0raoZREStDberw&submissionId=a1264fe3-20da-2e16-b0c3-f8d88d22aa7d">
              <img src="./assets/images/icons/linkedin-icon.png" alt="linkedin icon" class="landing-icons">
            </a>
            <a href="https://devpost.com/Lemos00?ref_content=user-portfolio&ref_feature=portfolio&ref_medium=global-nav">
              <img src="./assets/images/icons/devpost-png.png" alt="devpost icon" class="landing-icons">
            </a>
            <a href="mailto:webmaster@example.com">
              <img src="./assets/images/icons/mail-logo.png" alt="devpost icon" class="landing-icons">
            </a>
          </div>
        </div>
    </header>
    <AboutMe></AboutMe>
    <Skills></Skills>
    <Experience></Experience>
    <Projects></Projects>
    <Awards></Awards>
  </div>
</template>

<script>
import Skills from './components/Skills.vue'
import AboutMe from './components/AboutMe.vue'
import Awards from './components/Awards.vue'
import Projects from './components/Projects.vue'
import Experience from './components/Experience.vue'
export default {
  name: 'App',
  components: { 
    Skills,
    AboutMe,
    Awards,
    Projects,
    Experience
  },
  data() {
    return {
      menuSelected: false
    }
  },
  computed: {
    menuClass() {
      if (this.menuSelected === true) {
        return 'menu-toggler open'
      } else {
        return 'menu-toggler'
      }
    },
    navClass() {
      if (this.menuSelected === true) {
        return 'top-nav open'
      } else {
        return 'top-nav'
      }    
    }
  },
  methods: {
    changeMenu() {
      if (typeof this.menuSelected === Object) {
        this.menuSelected = false
      }
      this.menuSelected = !this.menuSelected
    }
  }
}
</script>

<style>
@import './assets/styles/main.css';
</style>
