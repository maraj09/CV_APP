<template>
    <div>
        <!-- Home Start  -----------------------------------------------------------
			----------------------------------------------------------------------->
        <section class="panel b-blue" id="1">
            <article class="panel__wrapper">
                <div class="panel__content" :class="{ 'panel__content--active': isLoad }">
                    <!-- Using Vue Bind Class To see nav when scroll -->
                    <div class="container">
                        <div class="row">
                            <div class="col-md-10 col-md-offset-1 ">
                                <div class="home-content">
                                    <div class="home-content-body">
                                        <p>Hi, My name is</p>
                                        <h2>Hunter.</h2>
                                        <h1>I build things for the internet.</h1>
                                        <p>
                                            Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio, error? Rerum nesciunt ipsum laboriosam,<a href="">temporibus</a> dolore, inventore
                                            atque nobis modi ipsa mollitia libero aliquid nihil magni. Quidem cum debitis et?
                                        </p>
                                        <a href="#2"><button>Discover More</button></a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </article>
        </section>
        <!-- Home End  -----------------------------------------------------------
			----------------------------------------------------------------------->
    </div>
</template>

<script>
export default {
    data() {
        return {
            isLoad: false,
        };
    },
    methods: {
        onWindowLoad() {
            this.isLoad = true;
            this.$emit("isHome");
        },
        home(){
            this.$emit("isHome");
        }
    },
    mounted() {
        // Auto Calling A method when scroll the page
        window.addEventListener("load", this.onWindowLoad);
        window.addEventListener("scroll", this.home);
    },
};
</script>

<style>

</style>
