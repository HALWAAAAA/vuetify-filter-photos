<template>
  <v-app>
    
    <SideBar @selectOption="onSelectOption"></SideBar>
    <v-main>
      <ImageGallery :isWithColor="isWithColor"></ImageGallery>
    </v-main>
  </v-app>
</template>

<script setup>
import SideBar from "./components/SideBar";
import ImageGallery from "./components/ImageGallery";
import {ref} from "vue";

const isWithColor = ref(true);
const onSelectOption = (isColor)=>{
  isWithColor.value = isColor
}
</script>
