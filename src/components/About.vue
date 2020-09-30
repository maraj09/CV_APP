<template>
    <div>
        <!-- About Us ----------------------------------------------------------------
        ------------------------------------------------------------------------------>
        <section class="panel b-yellow" id="2">
            <article class="panel__wrapper">
                <div class="panel__content " :class="{ 'panel__content--active': inAbout }">
                    <!-- Using Vue Bind Class To see nav when scroll -->
                    <div class="container">
                        <div class="row">
                            <div class="col-md-12 ">
                                <div class="about-content">
                                    <div class=" about-content-body">
                                        <h3><span style="color: rgb(255, 123, 0); margin-right:5px">01. </span>About Me</h3>
                                        <div class="side_line"></div>
                                        <div class="row about-left col-sm-6 ">
                                            <div class="left-span">
                                                <span>
                                                    Hello! I'm Hunter, a fullstack engineer living in Karlsruhe, Germany who enjoys building things that live on the internet and people's devices. I
                                                    develop exceptional web & mobile apps that provide intuitive, pixel-perfect user interfaces with efficient and modern backends for more than 5
                                                    years.
                                                </span>
                                                <p>
                                                    Here are a few technologies I've been working with recently:
                                                </p>
                                            </div>
                                            <div class="left-ul">
                                                <ul>
                                                    <li class="about_skill arrow">JavaScript (ES6+)</li>
                                                    <li class="about_skill arrow">HTML & (S)CSS</li>
                                                    <li class="about_skill arrow">Node.js</li>
                                                    <li class="about_skill arrow">Redux</li>
                                                    <li class="about_skill arrow">Python/Flask</li>
                                                    <li class="about_skill arrow">Docker</li>
                                                    <li class="about_skill arrow">TypeScript</li>
                                                    <li class="about_skill arrow">RxJS</li>
                                                    <li class="about_skill arrow">Express</li>
                                                    <li class="about_skill arrow">GraphQL/REST</li>
                                                    <li class="about_skill arrow">Jest/Enzyme/RTL</li>
                                                    <li class="about_skill arrow">Vue</li>
                                                </ul>
                                            </div>
                                        </div>
                                        <div class="col-sm-6 about-right">
                                            <a class="imglink" href="">
                                                <img class="portrait" src="../assets/img/pi_2.jpg" alt="" />
                                                <div class="portrait_frame"></div>
                                            </a>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </article>
        </section>
        <!-- About Us End ----------------------------------------------------------------
        ------------------------------------------------------------------------------>
        <Nav :isAbout="inAbout" />
    </div>
</template>
<script>
import Nav from "./Nav.vue";

export default {
    components: {
        Nav,
    },
    data() {
        return {
            inAbout: false,
        };
    },
    methods: {
        loadScroll() {
            // getting the current scroll and vh position
            var windowHeight = window.innerHeight;
            var scrollPosition = window.pageYOffset;
            if (scrollPosition > windowHeight * 0.75) {
                this.inAbout = true;
                this.$emit("markAbout");
            } else {
                this.inAbout = false;
            }
        },
    },
    mounted() {
        // Auto Calling A method when scroll the page
        window.addEventListener("scroll", this.loadScroll);
    },
};
</script>

<style>
.about-content-body {
    position: relative;
    color: white;
    width: 100%;
    margin-left: 50px;
    padding-top: 15vh;
    text-align: left;
    line-height: 1.1;
}
.about-content-body h3 {
    font-size: 25px;
    font-weight: 700;
}
.side_line {
    background: rgb(122, 122, 122);
    height: 1px;
    width: 50%;
    max-width: 300px;
    margin-top: -25px;
    margin-left: 180px;
}
.left-span {
    margin-top: 50px;
    color: rgb(199, 199, 199);
    width: 80%;
}
.left-span span {
    font-size: 17px;
    position: relative;
    line-height: 1.7;
    word-spacing: 3px;
}
.left-span p {
    font-size: 17px;
    margin-top: 25px;
    width: 100%;
}

.arrow::before {
    content: "▹";
    color: rgb(255, 123, 0);
    font-size: 16px;
    padding-right: 10px;
}
.left-ul {
    margin-top: 15px;
    min-width: 450px;
    font-size: 14px;
    color: rgb(199, 199, 199);
}
.about_skill {
    display: inline-block;
    width: 50%;
    padding: 5px 0;
}
.portrait:hover {
    filter: sepia(0%);
}
.about-right {
    position: relative;
}
.portrait {
    position: absolute;
    width: 55%;
    min-width: 210px;
    top: 55px;
    left: 25%;
    height: 380px;
    margin: 0 auto !important;
    z-index: 2;
    filter: sepia(90%);
    transition: 0.3s;
}
.portrait_frame {
    position: absolute;
    left: 30%;
    top: 75px;
    height: 100px;
    border: 3px solid rgb(255, 123, 0);
    transition: 0.3s;
    width: 55%;
    min-width: 210px;
    height: 380px;
}
.imglink:hover .portrait_frame {
    top: 69px;
    left: 28%;
}
@media (max-width: 1199px) {
    .about-content-body {
        padding-top: 7vh;
    }
    .portrait {
        height: 300px;
        width: 45%;
    }
    .portrait_frame {
        height: 300px;
        width: 45%;
    }
}
@media (max-width: 768px) {
    .about-content-body {
        padding-top: 3vh;
    }
    .portrait {
        height: 250px;
        width: 30%;
        top: 10px;
    }
    .portrait_frame {
        height: 250px;
        width: 30%;
        top: 30px;
    }
    .about-right {
        text-align: center;
        margin-top: 5vh;
        right: 7%;
    }
    .imglink:hover .portrait_frame {
        top: 25px;
        left: 27%;
    }
    .about-left {
        left:  5%;
        width: 98%;
    }
}
</style>
