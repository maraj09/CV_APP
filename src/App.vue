<template>
    <div>
        <Nav />
        <Home />
		<About/>
		<Project/>
		<Contact/>
        <Footer/>
    </div>
</template>

<script>
import Home from "./components/Home.vue";
import Nav from "./components/Nav.vue";
import About from './components/About.vue';
import Project from './components/Project.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
export default {
    components: {
    Footer,
		Project,
    About,
        Nav,
        Home,
    Contact,
    },
};
</script>

<style >
html {
	scroll-behavior: smooth;
}
</style>
