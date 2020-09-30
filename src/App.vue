<template>
    <div>
        <!-- Calling All The Components -->
        <div class="topNav" :class="{ afterscroll: afterscroll }">
            <!-- For show nav when scrolls -->
            <a href>
                <img src="./assets/ryzen_nav.png"  alt srcset />
            </a>
            <div class="topnav-iteams">
                <a href>
                    <button class="cv_btn">C.V</button>
                </a>
                <a href>
                    <button class="resume_btn">Resume</button>
                </a>
            </div>
        </div>
        <nav class="nav">
            <div @click="toggleMenu()" :class="{ 'burger--active': isClicked }"  class="burger">
                <!-- Add class for change burger symbol -->
                <div class="burger__patty"></div>
            </div>
            <ul class="nav__list" :class="{ 'nav__list--active': isClicked }">
                <li title="Home" class="nav__item">
                    <a href="#1" :class="{ nav__link__active: isHome }" class="nav__link c-blue">
                        <!-- Add class for see which  page  is open -->
                        <img src="img/home-icon.png" alt />
                        <span class="tooltiptext">Home</span>
                    </a>
                </li>
                <li title="About" class="nav__item">
                    <a href="#2" :class="{ nav__link__active: isAbout }" class="nav__link c-yellow scrolly">
                        <!-- Add class for see which  page  is open -->
                        <img src="img/about-icon.png" alt />
                        <span class="tooltiptext">About</span>
                    </a>
                </li>
                <li title="Projects" class="nav__item">
                    <a href="#3" :class="{ nav__link__active: isProject }" class="nav__link c-red">
                        <!-- Add class for see which  page  is open -->
                        <img src="img/projects-icon.png" alt />
                        <span class="tooltiptext">Projects</span>
                    </a>
                </li>
                <li title="Contact" class="nav__item">
                    <a href="#4" :class="{ nav__link__active: isContact }" class="nav__link c-green">
                        <!-- Add class for see which  page  is open -->
                        <img src="img/contact-icon.png" alt />
                        <span class="tooltiptext">Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
        <Home       @isHome='markHome' /> <!--  @ or V-bind comming from commponents which is calling methods -->
        <About      @isAbout='markAbout' />
        <Project    @isProject='markProject' />
        <Contact    @isContact='markContact'/>
        <Footer/>
    </div>
</template>

<script>
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Project from "./components/Project.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
export default {
    data() {
        return {
            isClicked: false,
            y: "",
            h: "",
            afterscroll: false,
            isHome: false,
            isAbout: false,
            isProject: false,
            isContact: false,
        };
    },
    components: {
        Footer,
        Project,
        About,
        Home,
        Contact,
    },
    methods: {
        markContact(){
            this.isContact = true;
            this.isProject = false;
            this.isAbout   = false;
            this.isHome    = false;
        },
        markProject(){
            this.isProject = true;
            this.isContact = false;
            this.isAbout   = false;
            this.isHome    = false;
        },
        markAbout(){
            this.isAbout   = true;
            this.isProject = false;
            this.isContact = false;
            this.isHome    = false;
        },
        markHome(){
            this.isHome    = true;
            this.isAbout   = false;
            this.isProject = false;
            this.isContact = false;
        },
        toggleMenu() {
            this.isClicked = !this.isClicked;
        },
        scrollpos() {
            this.y = window.pageYOffset;
            this.h = window.innerHeight;
        },
        addNav() {
            if (this.y > 0) {
                this.afterscroll = true;
            } else {
                this.afterscroll = false;
            }
        },
    },
    mounted() {
        // Auto Calling A method when scroll the page
        window.addEventListener("scroll", this.scrollpos);
        window.addEventListener("scroll", this.addNav);
    },
};
</script>

<style>
html {
    scroll-behavior: smooth;
}
.afterscroll {
    margin-top: 0px;
    background-color: #000000af;
}
.nav__link__active {
    background: #fa5252;
}
.tooltiptext {
    position: absolute;
    color: white;
    font-size: 22px;
    font-weight: 700;
    visibility: hidden;
    transition: 0.01s;
    bottom: 25%;
}
@media (max-width: 1200px) {
    .tooltiptext {
        bottom: 20%;
    }
}
@media (max-width: 768px) {
    .tooltiptext {
        bottom: 17%;
        font-size: 18px;
    }
}
</style>
