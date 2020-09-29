<template>
    <div>
        <!-- Home Start  -----------------------------------------------------------
			----------------------------------------------------------------------->
        <section class="panel b-blue" id="1">
            <article class="panel__wrapper">
                <div class="panel__content" :class="{ 'panel__content--active': isLoad }">
                    <div class="container">
                        <div class="row">
                            <div class="col-md-12">
                                <div class="home-content">
                                    <div class="home-content-body">
                                    <p>Hi, My name is </p>
                                    <h2>Hunter.</h2>
                                    <h1>I build things for the internet.</h1>
                                    <p >Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio, error? Rerum nesciunt ipsum laboriosam,<a href="">temporibus</a>  dolore, inventore atque nobis modi ipsa mollitia libero aliquid nihil magni. Quidem cum debitis et?</p>
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
        },
    },
    mounted() {
        window.addEventListener("load", this.onWindowLoad);
    },
};
</script>

<style >
    .home-content-body{
        position: relative;
        color: white;
        width: 100% ;
        margin-left: 50px;
        padding-top: 20vh;
        text-align: left;
        line-height: 1.1;
    }
    .home-content-body h1{
        padding-top: 0;
        font-size: 50px;
        font-weight: 700;
        color: rgba(185, 185, 185, 0.925);
        margin-bottom: 50px;
    }
    .home-content-body p:nth-of-type(1){
        color: rgb(255, 123, 0);
        font-size: 18px;
        margin-left: 2px;
        word-spacing: 5px;
    }
    .home-content-body a{
        color: rgb(255, 123, 0);

    }
    .home-content-body p:nth-of-type(2){
        color:rgba(185, 185, 185, 0.925);
        font-size: 18px ;
        width: 50%;
        margin-left: 2px;
        min-width: 400px;

    } 
    .home-content-body h2{
        font-size: 60px;
        font-weight: bold;
    }
    .home-content-body button{
        height: 50px;
        background: transparent;
        outline: none !important;
        border: 2px solid rgb(255, 123, 0);
        border-radius: 3px;
        padding: 10px 45px;
        margin-left: 2px;
        margin-top: 50px;
        color: white;
        transition: .3s;
    }
    .home-content-body button:hover{
        background: rgba(255, 166, 0, 0.267);
    }
    @media(max-width: 1200px){
        .home-content-body{
            padding-top: 10vh;
            margin-left: 25px;

        }
    }
    @media(max-width: 768px){
        .home-content-body{
            padding-top: 20vh;
            
        }
        .home-content-body h1{
        padding-top: 0;
        font-size: 40px;
        }
        .home-content-body button{
        margin-top: 25px;
        margin-bottom: 50px;
        }
    @media(max-width: 480px){
        .home-content-body{
            padding-top: 17vh;
            margin-left: -10px;
        }
        .home-content-body p:nth-of-type(2){
            min-width: 350px;
        }
    }
    }
</style>
