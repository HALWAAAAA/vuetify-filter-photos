<template>
  <v-navigation-drawer expand-on-hover rail>
    <v-list>
      <v-list-item
        prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
        subtitle="taras.kotsyuba2003@gmailcom"
        title="Taras K"
      ></v-list-item>
    </v-list>
    <v-divider></v-divider>
<v-list density="compact" nav>
    <v-list-item prepend-icon="mdi-image" title="Color Gallery" value="color" @click="selectOption(true)"></v-list-item>
    <v-list-item prepend-icon="mdi-dialpad" title="Grayspace Gallery" value="color" @click="selectOption(false)"></v-list-item>
</v-list>
  </v-navigation-drawer>
</template>

<script setup>
const emits = defineEmits(['selectOption']);

const selectOption = (isColor) =>{
    emits("selectOption", isColor)
}
</script>