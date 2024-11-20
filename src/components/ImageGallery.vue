<template>
  <v-card class="ma-5 my-2 pa-3">
    <v-row>
      <v-col cols="4" v-for="n in 200" sm="3" md="2" lg="2">
        <v-card @click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${pr.isWithColor ? '' : '&grayscale'}`)">
          <v-img
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${pr.isWithColor ? '' : '&grayscale'}`"
            aspect-ratio="1"
            cover
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${pr.isWithColor ? '' : '&grayscale'}`"
          >
            <template v-slot:placeholder>
              <v-row align="center" class="fill-height ma-0" justify="center">
                <v-progress-circular
                  color="grey-lighten-5"
                  indeterminate
                ></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>
<script setup>
const pr = defineProps(["isWithColor"]);
const copyUrl =async (url)=>{
    await navigator.clipboard.writeText(url)
}
</script>