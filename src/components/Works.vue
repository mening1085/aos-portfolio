<template>
  <div class="bg-white">
    <div
      class="container mx-auto min-h-[900px] flex items-center justify-center py-[9rem]"
    >
      <div>
        <div class="flex justify-center">
          <div
            data-aos="fade-right"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            class="w-[490px] text-center mb-6"
          >
            <div
              class="text-[6rem] uppercase work-heading font-semibold border-b-amber-300"
            >
              My Work
            </div>
            <div class="-mt-4 text-right text-3xl">awesome projects</div>
          </div>
        </div>

        <div class="flex justify-center gap-10 h-[50px] mb-4 mt-4">
          <div
            v-for="(type, i) in types"
            :key="i"
            @click="handleClickType(type)"
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
          >
            <div
              class="text-xl uppercase font-semibold cursor-pointer hover:border-b-4 hover:border-b-amber-300 transition-all duration-100 ease-in-out"
              :class="
                typeSelect === type ? 'border-b-4 border-b-amber-300' : ''
              "
            >
              {{ type }}
            </div>
          </div>
        </div>

        <!-- gallery -->
        <div class="flex flex-wrap" v-if="typeSelect == 'all'">
          <div
            v-for="(item, i) in workList"
            :key="i"
            class="basis-1/1 xs:basis-1/2 md:basis-1/3 p-4 min-w-[480px]"
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
          >
            <div class="relative">
              <img
                :src="item.image"
                class="hover-image-work object-cover w-full shadow-xl 2xl:h-[480px] xl:h-[394px] lg:h-[310px] md:h-[220px] sm:h-[160px] xs:h-[80px] hover:rotate-3 hover:scale-105 transition-all duration-500 ease-in-out"
              />

              <div
                class="work-desc absolute bottom-0 left-0 w-full h-[50px] bg-black text-amber-300 bg-opacity-90 flex items-center justify-center opacity-0 transition-all duration-500 ease-in-out hover:opacity-100"
              >
                {{ item.name }}
              </div>
            </div>
          </div>
        </div>

        <div class="flex flex-wrap" v-if="typeSelect == 'web'">
          <div
            v-for="(item, i) in workList"
            :key="i"
            class="basis-1/1 xs:basis-1/2 md:basis-1/3 p-4 min-w-[480px]"
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
          >
            <div class="relative">
              <img
                :src="item.image"
                class="hover-image-work object-cover w-full shadow-xl 2xl:h-[480px] xl:h-[394px] lg:h-[310px] md:h-[220px] sm:h-[160px] xs:h-[80px] hover:rotate-3 hover:scale-105 transition-all duration-500 ease-in-out"
              />

              <div
                class="work-desc absolute bottom-0 left-0 w-full h-[50px] bg-black text-amber-300 bg-opacity-90 flex items-center justify-center opacity-0 transition-all duration-500 ease-in-out hover:opacity-100"
              >
                {{ item.name }}
              </div>
            </div>
          </div>
        </div>

        <div class="flex flex-wrap" v-if="typeSelect == 'app'">
          <div
            v-for="(item, i) in workList"
            :key="i"
            class="basis-1/1 xs:basis-1/2 md:basis-1/3 p-4 min-w-[480px]"
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
          >
            <div class="relative">
              <img
                :src="item.image"
                class="hover-image-work object-cover w-full shadow-xl 2xl:h-[480px] xl:h-[394px] lg:h-[310px] md:h-[220px] sm:h-[160px] xs:h-[80px] hover:rotate-3 hover:scale-105 transition-all duration-500 ease-in-out"
              />

              <div
                class="work-desc absolute bottom-0 left-0 w-full h-[50px] bg-black text-amber-300 bg-opacity-90 flex items-center justify-center opacity-0 transition-all duration-500 ease-in-out hover:opacity-100"
              >
                {{ item.name }}
              </div>
            </div>
          </div>
        </div>

        <!-- load more -->
        <div
          data-aos="fade-up"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
          class="flex justify-center mt-12"
        >
          <button
            v-if="!loadMore && typeSelect !== 'app'"
            @click="loadMore = true"
            class="bg-black px-8 py-3 rounded-full text-white font-semibold hover:bg-amber-400 transition-all duration-500 ease-in-out shadow-xl w-[200px] uppercase"
          >
            Load More
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from "vue";
import image1 from "../assets/images/project/cover/e-office.jpg";
import image2 from "../assets/images/project/cover/xfas.png";
import image3 from "../assets/images/project/cover/thaiwara.png";
import image4 from "../assets/images/project/cover/sut.png";
import image5 from "../assets/images/project/cover/fcard.png";
import image6 from "../assets/images/project/cover/sleep-app.png";
import image7 from "../assets/images/project/cover/franchise-portal.png";
import image8 from "../assets/images/project/cover/avatar-aeon.jpg";
import image9 from "../assets/images/project/cover/ditp.png";
import image10 from "../assets/images/project/cover/powerpod.png";
import image11 from "../assets/images/project/cover/pmuc.png";
import image12 from "../assets/images/project/cover/oscc-consult.png";
import image13 from "../assets/images/project/cover/tnl-driver.png";
import image14 from "../assets/images/project/cover/progo.png";
import image15 from "../assets/images/project/cover/bedo-ai.png";
import image16 from "../assets/images/project/cover/mvtv.png";
import image17 from "../assets/images/project/cover/tnl.png";
import image18 from "../assets/images/project/cover/cea-connect.png";
import image19 from "../assets/images/project/cover/irbrta.png";
import image20 from "../assets/images/project/cover/med-tools.png";
import image21 from "../assets/images/project/cover/sat.png";

const works = ref([
  {
    name: "สำนักงานเศรษฐกิจการเกษตร E-Office Automation",
    image: image1,
    type: "web",
  },
  {
    name: "XFAS",
    image: image2,
    type: "web",
  },
  {
    name: "Thai Wara",
    image: image3,
    type: "web",
  },
  {
    name: "SUT",
    image: image4,
    type: "web",
  },
  {
    name: "Bear Wash F-Card",
    image: image5,
    type: "web",
  },
  {
    name: "นิทรารมณ์",
    image: image6,
    type: "app",
  },
  {
    name: "ระบบ Franchise Portal",
    image: image7,
    type: "web",
  },
  {
    name: "AEON METAVERSE Virtual Party 2022",
    image: image8,
    type: "web",
  },
  {
    name: "Thai Trade USA",
    image: image9,
    type: "web",
  },
  {
    name: "Powerpod Fitness Club",
    image: image10,
    type: "web",
  },
  {
    name: "PMUC MediPod System",
    image: image11,
    type: "web",
  },
  {
    name: "OSCC Consulting",
    image: image12,
    type: "web",
  },
  {
    name: "TN Logistic System (Driver)",
    image: image13,
    type: "app",
  },
  {
    name: "Gosure Online",
    image: image14,
    type: "web",
  },
  {
    name: "Biodiversity Big data",
    image: image15,
    type: "web",
  },
  {
    name: "MVTV Authen Streaming",
    image: image16,
    type: "web",
  },
  {
    name: "TN Logistic System",
    image: image17,
    type: "web",
  },
  {
    name: "TCDC Connect by CEA",
    image: image18,
    type: "web",
  },
  {
    name: "ระบบจัดการโครงการวิจัยกรมแพทย์ทหารบก(irbrta)",
    image: image19,
    type: "web",
  },
  {
    name: "ระบบฐานข้อมูลกลางคุณลักษณะเฉพาะสิ่งสิ่อุปกรณ์สายแพทย์",
    image: image20,
    type: "web",
  },
  {
    name: "ระบบรายงานผู้บาดเจ็บหรือเสียชีวิตจากการตกน้ำ จมน้ำ",
    image: image21,
    type: "web",
  },
]);

const loadMore = ref(false);
const types = ref(["all", "web", "app"]);
const typeSelect = ref("all");
const workList = computed(() => {
  if (loadMore.value) {
    switch (typeSelect.value) {
      case "all":
        return works.value;
      case "web":
        return works.value.filter((item) => item.type === "web");
      case "app":
        return works.value.filter((item) => item.type === "app");
      default:
        return works.value;
    }
  } else {
    console.log("loadMore", typeSelect.value);
    switch (typeSelect.value) {
      case "all":
        return works.value.slice(0, 9);
      case "web":
        return works.value.filter((item) => item.type === "web").slice(0, 9);
      case "app":
        return works.value.filter((item) => item.type === "app").slice(0, 9);
      default:
        return works.value.slice(0, 9);
    }
  }
});

const handleClickType = (type) => {
  console.log("handleClick", type);
  typeSelect.value = type;
  loadMore.value = false;
};
</script>

<style lang="scss">
.work-heading {
  line-height: 15px;
  border-bottom: 36px;
  border-style: double;
}
.hover-image-work {
  filter: grayscale(100%);
  transition: all 0.5s ease-in-out;
}

.hover-image-work:hover {
  filter: grayscale(0%);
  transform: rotate(3deg) scale(1.05);
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);

  & ~ .work-desc {
    opacity: 100;
    transform: rotate(3deg) scale(1.05);
    bottom: -10px;
    left: -11px;
  }
}
</style>
