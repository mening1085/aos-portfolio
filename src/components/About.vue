<template>
  <div class="bg-gray-200 relative overflow-hidden">
    <img
      class="absolute top-0 bg-blog"
      src="../assets/images/banner.webp"
      alt=""
    />

    <div
      class="container mx-auto h-[900px] flex items-center justify-center relative"
    >
      <!-- <Icon
        data-aos="fade-right"
        data-aos-delay="1500"
        data-aos-duration="1000"
        data-aos-easing="ease-in-out"
        icon="material-symbols:arrows-more-down"
        class="text-gray-300 text-[23rem] absolute top-0 right-[5%]"
      /> -->
      <div class="flex px-12 pt-[6rem] pb-[8rem]">
        <div class="basis-1/2 flex justify-center">
          <div
            data-aos="fade-right"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            class="h-[600px] w-[500px] bg-black absolute"
          ></div>
          <div
            data-aos="fade-left"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            class="h-[600px] w-[500px] mt-10 -mr-24"
          >
            <Carousel :autoplay="50000" :wrap-around="true" :items-to-show="1">
              <Slide v-for="slide in slides" :key="slide">
                <img
                  style="height: 600px; width: 100%"
                  :src="slide"
                  class="hover-image object-cover object-top shadow-xl"
                  alt=""
                />
              </Slide>
            </Carousel>
          </div>
        </div>
        <div class="basis-1/2 pr-12 h-[600px] flex items-center">
          <div>
            <div
              data-aos="fade-right"
              data-aos-delay="1000"
              data-aos-duration="1000"
              data-aos-easing="ease-in-out"
              class="w-[290px] text-right mb-6"
            >
              <div class="mb-7 text-3xl">who am i</div>
              <div
                class="text-[6rem] uppercase about-heading font-semibold border-b-amber-300"
              >
                Hello
              </div>
            </div>

            <div
              data-aos="fade-left"
              data-aos-delay="1000"
              data-aos-duration="1000"
              data-aos-easing="ease-in-out"
              class="mb-6"
            >
              I am a Full stack developer, Every day I always think that I don't
              just come to work to make money. But I'm here to create a work.
              Because working in the world of programming isn't just a job. But
              it was also an exciting adventure. Full of technology that is
              constantly changing.
            </div>

            <div
              data-aos="fade-left"
              data-aos-delay="1000"
              data-aos-duration="1000"
              data-aos-easing="ease-in-out"
            >
              I challenge myself every day to create better products for people
              to use. And I will never stop improving. I am committed to
              continuous self-improvement. Be it coding or web development.
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
import { ref } from "vue";
import image1 from "../assets/images/me_1.png";
import image2 from "../assets/images/me.jpeg";
import image3 from "../assets/images/me_7.jpeg";
import image4 from "../assets/images/me_4.jpeg";
import image5 from "../assets/images/me_3.jpeg";
import image6 from "../assets/images/me_2.png";
import { Icon } from "@iconify/vue";

const slides = ref([image1, image2, image3, image4, image5, image6]);
</script>

<style>
.about-heading {
  line-height: 15px;
  border-bottom: 36px;
  border-style: double;
}
</style>
