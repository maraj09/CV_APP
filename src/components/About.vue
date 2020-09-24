<template>
    <div>
        <!-- About Us ----------------------------------------------------------------
        ------------------------------------------------------------------------------>
        <section class="panel b-yellow" id="2">
            <article class="panel__wrapper">
                <div class="panel__content " :class="{'panel__content--active' : inAbout }">
                    <div class="container">
                        <div class="row">
                            <div class="col-md-12 ">
                                <div class="about-content">
                                    <div class="heading">
                                        <h4>About us</h4>
                                    </div>
                                    <div class="row">
                                        <div class="col-md-12">
                                            <div class="about-box-content">
                                                <img
                                                    src="img/about-image.png"
                                                    alt=""
                                                />
                                            </div>
                                        </div>
                                        <div class="col-md-7 col-md-offset-5">
                                            <div class="about-box-text">
                                                <h4>Curabitur varius sapien</h4>
                                                <p>
                                                    Please feel free to contact
                                                    us if you have any question
                                                    or suggestion about our free
                                                    templates. Thank you.
                                                    Template redistribution is
                                                    <strong>NOT allowed</strong
                                                    >.
                                                </p>
                                                <div class="primary-button">
                                                    <a href="#3"
                                                        >Discover More</a
                                                    >
                                                </div>
                                            </div>
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
import Nav from './Nav.vue';

export default {
    components: {
        Nav,
    },
    data() {
        return {
            inAbout : false,
        }
    },
    methods: {
        loadScroll() {
            var windowHeight = window.innerHeight
            var scrollPosition = window.pageYOffset 
            if (scrollPosition > windowHeight*.75 ) {
                this.inAbout = true
            }else{
                this.inAbout = false
            }
        }
    },
    mounted () {
        window.addEventListener("scroll", this.loadScroll);
    },
};
</script>

<style lang="scss" scoped></style>
