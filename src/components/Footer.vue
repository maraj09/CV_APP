<template>
    <div>
        <div class="social">
            <ul>
                <li>
                    <a href=""><i class="fab fa-github social_icon"></i></a>
                </li>
                <li>
                    <a href=""><i class="fab fa-facebook-f social_icon"></i></a>
                </li>
                <li>
                    <a href=""><i class="fab fa-instagram social_icon"></i></a>
                </li>
                <li>
                    <a href=""><i class="fab fa-twitter social_icon "></i></a>
                </li>
            </ul>
        </div>
        <div class="footerline"></div>
    </div>
</template>

<script>
export default {};
</script>

<style>
.footerline {
    background-color: white;
    height: 100px;
    width: 1px;
    position: fixed;
    margin-left: 80px;
    bottom: 0;
}
.social {
    position: fixed;
    bottom: 100px;
    left: 0px;
    margin-left: 60px;
    text-align: center;
}
.social li {
    margin-bottom: 20px;
}
.social_icon {
    font-size: 40px;
    color: white;
    transition: 0.2s;
    padding-top: 17px;
}
.social_icon:hover {
        color: rgb(255, 123, 0);
    padding-top: 1px;
}
@media (max-width: 900px) {
    .topnav-iteams {
        margin-right: 70px !important;
    }
    .social {
        margin-left: 38px;
    }
    .footerline {
        margin-left: 50px !important;
    }
}
@media (max-width: 768px) {
    .footerline {
        display: none;
    }
    .social {
        position: relative;
        bottom: 0;
        margin: 0 auto;
        background: rgba(0, 0, 0, 0.918);
        height: 60px;
        text-align: left;
        
    }
    .social li {
        display: inline;
        margin-left: 13%;
        font-size: 35px;
    }
}
</style>
