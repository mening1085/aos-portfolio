<template>
  <div class="bg-gray-200 relative min-h-[500px] overflow-hidden parallax">
    <div
      class="container relative mx-auto flex items-center justify-center py-[8rem]"
    >
      <div>
        <div class="flex justify-center">
          <div
            data-aos="fade-left"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            class="w-[490px] mb-6"
          >
            <div class="text-3xl mb-6">interests/hobbies/free time</div>

            <div
              class="text-[6rem] uppercase work-heading font-semibold border-b-amber-300"
            >
              My Blog
            </div>
          </div>
        </div>

        <div class="mt-12">
          <Carousel :items-to-show="3" :autoplay="5000" :wrap-around="true">
            <Slide v-for="(post, i) in posts" :key="i">
              <div
                data-aos="fade-up"
                data-aos-duration="1000"
                data-aos-easing="ease-in-out"
                class="mb-6"
              >
                <div class="mb-4">
                  <img
                    :src="post.image"
                    class="w-full h-[300px] object-cover"
                    alt=""
                  />
                </div>
                <div class="mb-2 one-line">{{ post.title }}</div>
                <div class="text-sm">
                  <a :href="post.link" target="_blank">Read more</a>
                </div>
              </div>
            </Slide>
          </Carousel>

          <div
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            class="flex justify-center mt-12"
          >
            <a
              href="https://filmeverywhere.xmmeenn.com/"
              class="bg-black px-8 py-3 rounded-full text-white font-semibold hover:bg-amber-400 transition-all duration-500 ease-in-out shadow-xl w-[200px] uppercase text-center curser-pointer"
              target="_blank"
            >
              Go to blog
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

import image1 from "../assets/images/posts/hb-1.jpg";
import image2 from "../assets/images/posts/hb-2.jpg";
import image3 from "../assets/images/posts/hb-3.jpg";
import image4 from "../assets/images/posts/hb-4.jpg";
import image5 from "../assets/images/posts/hb-5.jpg";
import image6 from "../assets/images/posts/hb-6.jpg";

const posts = ref([
  {
    title: "ราคาฟิล์มแพงขึ้น เราก็ถ่ายน้อยลง 1 ม้วน 3 ทริป 3 จังหวัด",
    link: "https://filmeverywhere.xmmeenn.com/?p=877",
    image: image1,
  },
  {
    title: "ลองฟิล์ม KIRO-400 ที่สถานีหัวลำโพง",
    link: "https://filmeverywhere.xmmeenn.com/?p=783",
    image: image2,
  },
  {
    title: "Pentax Spotmatic SP x Kodak Vision 500D ลุยตลาดจตุจักร-ตึกแดง",
    link: "https://filmeverywhere.xmmeenn.com/?p=671",
    image: image3,
  },
  {
    title: "1 Day Trip 2021 at PATAYA With KISRA CORP",
    link: "https://filmeverywhere.xmmeenn.com/?p=494",
    image: image4,
  },
  {
    title: "คาเฟ่ดังในย่านอารีย์ (Gump Ari)",
    link: "https://filmeverywhere.xmmeenn.com/?p=291",
    image: image5,
  },
  {
    title: "จับ Nikon zoom 310 AF เดินถ่ายกับเพื่อน หอศิลป์/Gump Ari",
    link: "https://filmeverywhere.xmmeenn.com/?p=249",
    image: image6,
  },
]);
</script>

<style lang="scss">
.bg-blog {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  opacity: 0.2;
}
.parallax {
  position: relative;
  /* The image used */
}
.parallax::before {
  content: "";
  background-image: url("../assets/images/banner4.webp");
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  filter: blur(3px) contrast(1.2) opacity(0.2);
}
.one-line {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
