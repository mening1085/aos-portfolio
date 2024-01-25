<template>
  <div class="bg-black relative min-h-[500px] overflow-hidden text-white">
    <div class="container relative pt-[6rem] mx-auto">
      <div>
        <div
          data-aos="fade-up"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
          class="mb-6 flex justify-center"
        >
          <div>
            <span class="font-semibold text-3xl text-black px-3 bg-amber-300">
              Get in touch
            </span>

            <div class="text-[6rem] -mt-4 uppercase font-semibold text-white">
              contact
            </div>
          </div>
        </div>

        <div
          class="flex justify-center gap-16"
          data-aos="fade-up"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
        >
          <div class="flex items-center justify-center">
            <Icon icon="material-symbols:mail" class="text-3xl" />
            <div class="text-xl pl-1">mening1085@gmail.com</div>
          </div>
          <div class="flex items-center justify-center">
            <Icon icon="ic:baseline-phone" class="text-3xl" />
            <div class="text-xl pl-1">0812-3456-7890</div>
          </div>
          <div class="flex items-center justify-center">
            <Icon icon="bxs:map" class="text-3xl" />
            <div class="text-xl pl-1">Bangkok, Thailand 10220</div>
          </div>
        </div>

        <div
          data-aos="fade-up"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
        >
          <div class="flex justify-center items-center gap-6 mt-12">
            <a href="https://www.facebook.com/x.mmeenn/" target="_blank">
              <Icon icon="ic:baseline-facebook" class="text-[45px]" />
            </a>
            <a href="https://github.com/mening1085" target="_blank">
              <Icon icon="akar-icons:github-fill" class="text-[38px]" />
            </a>
            <a
              href="https://www.linkedin.com/in/kasem-tanson-92b2b51a2/"
              target="_blank"
            >
              <Icon
                icon="entypo-social:linkedin-with-circle"
                class="text-[42px]"
              />
            </a>
            <a href="https://www.instagram.com/x.mmeenn/" target="_blank">
              <Icon
                icon="entypo-social:instagram-with-circle"
                class="text-[42px]"
              />
            </a>
          </div>

          <div class="flex justify-center items-center gap-6 mt-12 text-white">
            Copyright © 2024. | XMMEENN
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Icon } from "@iconify/vue";
</script>

<style></style>
