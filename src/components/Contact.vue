<template>
    <div>
        <!-- Contact ----------------------------------------------------------
		------------------------------------------------------------------------------>
        <section class="panel b-green" id="4">
            <article class="panel__wrapper">
                <div class="panel__content " :class="{ 'panel__content--active': inContact }">
                    <!-- Using Vue Bind Class To see nav when scroll -->
                    <div class="container">
                        <div class="row">
                            <div class=" col-md-10 col-md-offset-1">
                                <div class="contact-content">
                                    <div class="heading">
                                        <h4>Contact us</h4>
                                    </div>
                                    <div class="row">
                                        <div class="col-md-12 ">
                                            <div class="contat-form">
                                                <form id="contact" action="" method="post">
                                                    <fieldset>
                                                        <input name="name" type="text" class="form-control" id="name" placeholder="Your Name" required="" />
                                                    </fieldset>
                                                    <fieldset>
                                                        <input name="email" type="email" class="form-control" id="email" placeholder="Email" required="" />
                                                    </fieldset>
                                                    <fieldset>
                                                        <textarea name="message" rows="6" class="form-control" id="message" placeholder="Message" required=""></textarea>
                                                    </fieldset>
                                                    <fieldset>
                                                        <button type="submit" id="form-submit" class="btn">
                                                            Send Message
                                                        </button>
                                                    </fieldset>
                                                </form>
                                            </div>
                                        </div>
                                        <div class="col-md-4">
                                            <div class="more-info">
                                                <p>
                                                    Nunc purus ligula, ullamcorper id velit id, vestibulum auc sapien. Sed quis mauris eget sem imperdiet rhoncus.<br /><br />
                                                    <em>880 Etiam mauris erat, <br />Vestibulum eu augue nec, 10940</em>
                                                </p>
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
        <!-- Contact end ----------------------------------------------------------
		------------------------------------------------------------------------------>
    </div>
</template>

<script>
export default {
    components: {},
    data() {
        return {
            inContact: false,
        };
    },
    methods: {
        loadScroll() {
            // getting the current scroll and vh position
            var windowHeight = window.innerHeight;
            var scrollPosition = window.pageYOffset;
            var browserH = screen.height;
            console.log(scrollPosition);
            if (browserH < 850) {
                if (scrollPosition > 2200) {
                    this.inContact = true;
                    this.$emit("isContact");
                } else {
                    this.inContact = false;
                }
            } else {
                if (scrollPosition > windowHeight * 2.5) {
                    this.inContact = true;
                    this.$emit("isContact");
                } else {
                    this.inContact = false;
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
.heading {
    padding-top: 25vh;
}
@media (max-width: 768px) {
    .heading {
        padding-top: 10vh;
    }
    .contact-content{
        width: 100vw;
    }
}
</style>
