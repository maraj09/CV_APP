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
                            <div class="col-md-10 col-md-offset-1">
                                <div class="about-content">
                                    <div class=" about-content-body">
                                        <h3>About Me</h3>
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
    </div>
</template>
<script>
export default {
    components: {},
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
            if (windowHeight < 850) {
                if (scrollPosition > 490) {
                    this.inAbout = true;
                    this.$emit("isAbout");
                } else {
                    this.inAbout = false;
                }
            } else {
                if (scrollPosition > windowHeight * 0.75) {
                    this.inAbout = true;
                    this.$emit("isAbout");
                } else {
                    this.inAbout = false;
                }
            }
        },
    },
    mounted() {
        // Auto Calling A method when scroll the page
        window.addEventListener("scroll", this.loadScroll);
    },
};
</script>

<style></style>
