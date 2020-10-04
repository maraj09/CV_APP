<template>
    <div>
        <!-- Project -------------------------------------------------------
		-------------------------------------------------------------------------->
        <section class="panel b-red" id="3">
            <article class="panel__wrapper">
                <div class="panel__content" :class="{ 'panel__content--active': inProject }">
                    <!-- Using Vue Bind Class To see nav when scroll -->
                    <div class="container">
                        <div class="row">
                            <div class="col-md-10 col-md-offset-1 ">
                                <div class="projects-content">
                                    <div class="projects-content-body">
                                        <div class="heading">
                                            <h4>Recent Projects</h4>
                                        </div>
                                        <div class="owl-carousel owl-theme projects-container">
                                            <div class="project-item">
                                                <a href="img/project-item-01.jpg" data-lightbox="image-1"><img src="img/project-item-01.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Work Smart</h4>
                                                    <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="project-item">
                                                <a href="img/project-item-02.jpg" data-lightbox="image-1"><img src="img/project-item-02.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Creative Idea</h4>
                                                    <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
                                                </div>
                                            </div>
                                            <div>
                                                <div class="project-item">
                                                    <a href="img/project-item-03.jpg" data-lightbox="image-1"><img src="img/project-item-03.jpg" alt=""/></a>
                                                    <div class="text-content">
                                                        <h4>New Thought</h4>
                                                        <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                        <div class="primary-button">
                                                            <a href="#">Discover More</a>
                                                        </div>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="project-item">
                                                <a href="img/project-item-04.jpg" data-lightbox="image-1"><img src="img/project-item-04.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Next Moment</h4>
                                                    <p>Lorem ipsum dolor sit amet, adipis scing elit etiam sit amet ante vehicula, aliquam</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="project-item">
                                                <a href="img/project-item-05.jpg" data-lightbox="image-1"><img src="img/project-item-05.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Artwork</h4>
                                                    <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="project-item">
                                                <a href="img/project-item-06.jpg" data-lightbox="image-1"><img src="img/project-item-06.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Sixth Box</h4>
                                                    <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
                                                </div>
                                            </div>
                                            <div class="project-item">
                                                <a href="img/project-item-07.jpg" data-lightbox="image-1"><img src="img/project-item-07.jpg" alt=""/></a>
                                                <div class="text-content">
                                                    <h4>Item #7</h4>
                                                    <p>Lorem ipsum dolor, adipis scing elit etiam ante vehicula, aliquam mauris in, luctus neque.</p>
                                                    <div class="primary-button">
                                                        <a href="#">Discover More</a>
                                                    </div>
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
        <!-- Project End -------------------------------------------------------
		-------------------------------------------------------------------------->
    </div>
</template>

<script>
export default {
    components: {},
    data() {
        return {
            inProject: false,
        };
    },
    methods: {
        loadScroll() {
            // getting the current scroll and vh position
            var windowHeight = window.innerHeight;
            var scrollPosition = window.pageYOffset;
            if (windowHeight < 850) {
                if (scrollPosition > 1400) {
                    this.inProject = true;
                    this.$emit("isProject");
                } else {
                    this.inProject = false;
                }
            } else {
                if (scrollPosition > windowHeight * 1.5) {
                    this.inProject = true;
                    this.$emit("isProject");
                } else {
                    this.inProject = false;
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

<style scoped>
</style>
