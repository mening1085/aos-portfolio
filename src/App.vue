<script setup>
import { onMounted } from "vue";
import Header from "./components/Header.vue";
import About from "./components/About.vue";
import Works from "./components/Works.vue";
import Blog from "./components/Blog.vue";
import Contact from "./components/Contact.vue";
import AOS from "aos";
import { ref } from "vue";

const headerRef = ref(null);
const aboutRef = ref(null);
const worksRef = ref(null);
const blogRef = ref(null);
const contactRef = ref(null);

onMounted(() => {
  AOS.init();

  headerRef.value.scrollIntoView({ behavior: "smooth" });

  // reset path url when refresh page
  console.log(window.location);
  if (window.location.hash) {
    window.history.pushState("", "", "/");
  }
});

const handleClick = (name) => {
  console.log("handleClick", name);
  if (name === "About") {
    aboutRef.value.scrollIntoView({ behavior: "smooth" });
  } else if (name === "Works") {
    worksRef.value.scrollIntoView({ behavior: "smooth" });
  } else if (name === "Header") {
    headerRef.value.scrollIntoView({ behavior: "smooth" });
  } else if (name === "Blog") {
    blogRef.value.scrollIntoView({ behavior: "smooth" });
  } else if (name === "Contact") {
    contactRef.value.scrollIntoView({ behavior: "smooth" });
  } else {
    headerRef.value.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<template>
  <div>
    <!-- Header -->
    <div ref="headerRef">
      <Header @event:clickMenu="handleClick" />
    </div>

    <!-- about me -->
    <div ref="aboutRef">
      <About />
    </div>

    <!-- Work -->
    <div ref="worksRef">
      <Works />
    </div>

    <!-- Blog -->
    <div ref="blogRef">
      <Blog />
    </div>

    <!-- Contact -->
    <div ref="contactRef">
      <Contact />
    </div>
  </div>
</template>

<style scoped></style>
