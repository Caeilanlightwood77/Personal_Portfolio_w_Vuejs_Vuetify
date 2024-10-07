<script>
export default {
  name: "HeroSection",
  data() {
    return {
      showMenu: false,
      isVisible: false,
    };
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    },
    scrollTo(target) {
      this.$scrollTo(target, 1000);
      this.showMenu = false;
    },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
    handleScroll() {
      this.isVisible = window.scrollY > 200; // Show button after scrolling 200px
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    // Updated from beforeDestroy to beforeUnmount
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<template>
  <section class="hero-section">
    <div class="left-content">
      <h1>Work Smarter</h1>
    </div>

    <button
      class="hamburger"
      @click="toggleMenu"
      aria-label="Toggle menu"
      :aria-expanded="showMenu.toString()"
    >
      <span :class="{ 'is-open': showMenu }"></span>
      <span :class="{ 'is-open': showMenu }"></span>
      <span :class="{ 'is-open': showMenu }"></span>
    </button>

    <nav class="nav-menu" :class="{ 'menu-open': showMenu }">
      <ul>
        <li><a href="#home" @click.prevent="scrollTo('#home')">Home</a></li>
        <li><a href="#about" @click.prevent="scrollTo('#about')">About</a></li>
        <li>
          <a href="#resume" @click.prevent="scrollTo('#resume')">Resume</a>
        </li>
        <li>
          <a href="#services" @click.prevent="scrollTo('#services')">Service</a>
        </li>
        <li class="dropdown">
          <a href="#projects" @click.prevent="scrollTo('#projects')"
            >Projects</a
          >
          <ul class="dropdown-menu">
            <li>
              <a href="#project1" @click.prevent="scrollTo('#project1')"
                >Athena (Personalized A.I)</a
              >
            </li>
            <li>
              <a href="#project2" @click.prevent="scrollTo('#project2')"
                >Simple Calculator</a
              >
            </li>
            <li>
              <a href="#project3" @click.prevent="scrollTo('#project3')"
                >Text-Based Game</a
              >
            </li>
          </ul>
        </li>
        <li>
          <a href="#contact" @click.prevent="scrollTo('#contact')">Contact</a>
        </li>
      </ul>
    </nav>

    <button
      class="scroll-to-top"
      v-if="isVisible"
      @click="scrollToTop"
      aria-label="Scroll to Top"
    >
      ↑
    </button>
  </section>
</template>

<style scoped>
.hero-section {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: black;
  color: white;
  padding: 20px 40px;
  z-index: 1000;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.left-content h1 {
  font-size: 2rem;
  margin: 0;
}

.nav-menu {
  display: flex;
}

.nav-menu ul {
  list-style-type: none;
  display: flex;
  gap: 20px;
  margin: 0;
  padding: 0;
}

.nav-menu ul li {
  position: relative;
}

.nav-menu ul li a {
  font-weight: bold;
  color: white;
  text-decoration: none;
  font-size: 1.5rem;
  position: relative;
  padding-bottom: 5px;
}

.nav-menu ul li a:hover {
  color: white;
}

.nav-menu ul li a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  height: 2px;
  width: 100%;
  background-color: white;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.3s ease;
}

.nav-menu ul li a:hover::after {
  transform: scaleX(1);
}

.nav-menu ul li .dropdown-menu {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #333;
  list-style: none;
  padding: 10px;
  min-width: 120px;
  transform: translateX(-100px);
}

.nav-menu ul li:hover .dropdown-menu {
  display: block;
}

.dropdown-menu li a {
  color: white;
  text-decoration: none;
  display: block;
  padding: 5px 10px;
  white-space: nowrap;
}

.dropdown-menu li a:hover {
  background-color: #555;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 4px;
  background: none;
  border: none;
  cursor: pointer;
}

.hamburger span {
  width: 25px;
  height: 3px;
  background-color: white;
  transition: all 0.3s ease;
}

.hamburger span.is-open:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger span.is-open:nth-child(2) {
  opacity: 0;
}

.hamburger span.is-open:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

.scroll-to-top {
  position: fixed;
  bottom: 30px; /* Distance from the bottom */
  right: 30px; /* Distance from the right */
  background-color: #343a40; /* Button background color */
  color: white; /* Button text color */
  border: none;
  border-radius: 50%;
  width: 50px; /* Button size */
  height: 50px; /* Button size */
  font-size: 24px; /* Icon size */
  cursor: pointer;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.3s;
}

.scroll-to-top:hover {
  background-color: #555; /* Change color on hover */
}

@media (max-width: 768px) {
  .nav-menu {
    display: none;
    position: absolute;
    top: 60px;
    right: 0;
    background-color: black;
    width: 80%;
    padding: 20px;
    text-align: right;
    transition: transform 0.3s ease;
  }

  .nav-menu.menu-open {
    display: block;
  }

  .nav-menu ul {
    flex-direction: column;
    gap: 15px;
    padding: 0;
    margin: 0;
  }

  .nav-menu ul li {
    width: 100%;
    text-align: right;
  }

  .nav-menu ul li .dropdown-menu {
    position: static;
    width: 100%;
    left: 0;
    transform: translateX(0);
    font-size: 2rem;
  }

  .hamburger {
    display: flex;
  }
}
</style>
