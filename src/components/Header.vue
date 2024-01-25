<template>
  <div class="absolute bottom-[25%] left-[10%] z-[1000] left-[4rem]">
    <div
      data-aos="fade-right"
      data-aos-delay="500"
      data-aos-duration="1000"
      data-aos-easing="ease-in-out"
      class="text-2xl font-bold uppercase mt-4 text-white"
    >
      Hi, My name is
    </div>
    <div
      data-aos="fade-right"
      data-aos-delay="800"
      data-aos-duration="1000"
      data-aos-easing="ease-in-out"
      class="text-8xl font-bold uppercase mt-4 text-white text-amber-300 mb-6 tracking-[10px] name"
    >
      Kasem Tanson
    </div>

    <div
      data-aos="fade-right"
      data-aos-delay="1100"
      data-aos-duration="1000"
      data-aos-easing="ease-in-out"
    >
      <span
        class="text-4xl font-bold uppercase mt-4 text-black bg-amber-300 px-6 tracking-[10px]"
      >
        Full Stack Developer
      </span>
    </div>
  </div>

  <div class="h-screen">
    <div
      class="fixed top-0 h-[60px] w-full z-[9999]"
      :class="showNavbar && lastScrollPosition > 64 ? '' : 'hidden-navbar'"
    >
      <Menu @handleClick="handleClick" :position="lastScrollPosition" />
    </div>

    <div class="flex">
      <div class="basis-1/3 banner-left">
        <div
          data-aos="fade-right"
          data-aos-duration="1000"
          data-aos-easing="ease-in-sine"
          class="text-3xl font-bold uppercase text-center mt-4 text-white"
        >
          Portfolio
        </div>

        <img
          src="../assets/images/mac1.png"
          class="w-full max-h-[1000px] h-[200%] object-cover macbook"
          alt=""
        />
      </div>

      <div class="basis-2/3 relative menu">
        <!-- menu -->
        <Menu @handleClick="handleClick" :position="lastScrollPosition" />

        <!-- banner -->
        <div>
          <img
            src="../assets/images/avatar2.jpeg"
            class="object-cover object-top hover-image absolutee bottom-0 z-0 banner-image"
            alt=""
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, defineEmits, onMounted, onBeforeUnmount } from "vue";
import Menu from "./Menu.vue";

const emit = defineEmits(["event:clickMenu"]);

const activeMenu = ref("Home");

const menu = [
  {
    name: "Home",
    link: "#header",
  },
  {
    name: "About",
    link: "#about",
  },
  {
    name: "Works",
    link: "#works",
  },
  {
    name: "Blog",
    link: "#blog",
  },
  {
    name: "Contact",
    link: "#contact",
  },
];

const handleClick = (name) => {
  emit("event:clickMenu", name);
};

const showNavbar = ref(true);
const lastScrollPosition = ref(0);

const OFFSET = 50; // Adjust the OFFSET value as needed

const onScroll = () => {
  if (window.pageYOffset < 0) {
    return;
  }

  if (Math.abs(window.pageYOffset - lastScrollPosition.value) < OFFSET) {
    return;
  }

  showNavbar.value = window.pageYOffset < lastScrollPosition.value;
  lastScrollPosition.value = window.pageYOffset;

  // console.log(lastScrollPosition.value);
};

onMounted(() => {
  lastScrollPosition.value = window.pageYOffset;
  window.addEventListener("scroll", onScroll);

  const viewportMeta = document.createElement("meta");
  viewportMeta.name = "viewport";
  viewportMeta.content = "width=device-width, initial-scale=1";
  document.head.appendChild(viewportMeta);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", onScroll);
});
</script>

<style lang="scss">
.menu-items {
  background-color: #000000a6;
}
.banner-left {
  background-color: #000000;
  color: #ffffff;
  filter: contrast(80%);
  height: 100vh;
}
.banner-image {
  height: calc(100vh - 60px);
  width: 100%;
}
.macbook {
  filter: brightness(0.1);
}

.menu {
  height: 60px;
  width: 100vw;
  position: fixed;
  //box-shadow: 0 2px 15px rgba(71, 120, 120, 0.5);
  transform: translate3d(0, 0, 0);
  transition: 0.1s all ease-out;
  z-index: 999;
}

.hidden-navbar {
  box-shadow: none;
  transform: translate3d(0, -100%, 0);
}
.name {
  text-shadow: 2px 0px 2px #000000;
  //-webkit-text-stroke-width: 1px;
  //-webkit-text-stroke-color: black;
}
</style>
