<template>
    <div>
        <!-- Contact ----------------------------------------------------------
		------------------------------------------------------------------------------>
        <section class="panel b-green" id="4">
            <article class="panel__wrapper">
                <div class="panel__content " :class="{'panel__content--active' : inContact }">
                    <div class="container">
                        <div class="row">
                            <div class="col-md-12" >
                                <div class="contact-content">
                                    <div class="heading">
                                        <h4>Contact us</h4>
                                    </div>
                                    <div class="row">
                                        <div class="col-md-8">
                                            <div class="contat-form">
                                                <form
                                                    id="contact"
                                                    action=""
                                                    method="post"
                                                >
                                                    <fieldset>
                                                        <input
                                                            name="name"
                                                            type="text"
                                                            class="form-control"
                                                            id="name"
                                                            placeholder="Your Name"
                                                            required=""
                                                        />
                                                    </fieldset>
                                                    <fieldset>
                                                        <input
                                                            name="email"
                                                            type="email"
                                                            class="form-control"
                                                            id="email"
                                                            placeholder="Email"
                                                            required=""
                                                        />
                                                    </fieldset>
                                                    <fieldset>
                                                        <textarea
                                                            name="message"
                                                            rows="6"
                                                            class="form-control"
                                                            id="message"
                                                            placeholder="Message"
                                                            required=""
                                                        ></textarea>
                                                    </fieldset>
                                                    <fieldset>
                                                        <button
                                                            type="submit"
                                                            id="form-submit"
                                                            class="btn"
                                                        >
                                                            Send Message
                                                        </button>
                                                    </fieldset>
                                                </form>
                                            </div>
                                        </div>
                                        <div class="col-md-4">
                                            <div class="more-info">
                                                <p>
                                                    Nunc purus ligula,
                                                    ullamcorper id velit id,
                                                    vestibulum auc sapien. Sed
                                                    quis mauris eget sem
                                                    imperdiet rhoncus.<br /><br />
                                                    <em
                                                        >880 Etiam mauris erat,
                                                        <br />Vestibulum eu
                                                        augue nec, 10940</em
                                                    >
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
    components: {
        
    },
    data() {
        return {
            inContact : false,
        }
    },
    methods: {
        loadScroll() {
            var windowHeight = window.innerHeight
            var scrollPosition = window.pageYOffset 
            if (scrollPosition > windowHeight * 2.8) {
                this.inContact = true
            }else{
                this.inContact = false
            }
        }
    },
    mounted () {
        window.addEventListener("scroll", this.loadScroll);
    },
};
</script>

<style lang="scss" scoped></style>
