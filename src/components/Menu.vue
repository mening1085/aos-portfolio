<template>
  <div
    class="menu-items h-[60px] flex items-center justify-end gap-16 pr-12 relative z-10"
  >
    <a
      v-for="(item, index) in menu"
      :key="index"
      class="flex-shrink-0 uppercase text-white font-semibold cursor-pointer"
      :class="{
        'border-b-amber-300 border-b-2': activeMenu === item.name,
        'hover:border-b-amber-300 hover:border-b-2': activeMenu !== item.name,
      }"
      @click="handleClick(item.name)"
    >
      {{ item.name }}
    </a>
  </div>
</template>

<script setup>
import { ref, defineEmits, defineProps, computed } from "vue";

const props = defineProps(["position"]);

const emit = defineEmits(["handleClick"]);

const menu = [
  {
    name: "Home",
  },
  {
    name: "About",
  },
  {
    name: "Works",
  },
  {
    name: "Blog",
  },
  {
    name: "Contact",
  },
];

const activeMenu = computed(() => {
  if (props.position < 820) {
    return "Home";
  } else if (props.position >= 820 && props.position < 2132) {
    return "About";
  } else if (props.position >= 2132 && props.position < 4000) {
    return "Works";
  } else if (props.position >= 3000 && props.position < 3000) {
    return "Blog";
  } else if (props.position >= 3000) {
    return "Contact";
  }
});

const handleClick = (name) => {
  emit("handleClick", name);
};
</script>

<style>
.menu {
  background-color: #0000005e;
}
</style>
