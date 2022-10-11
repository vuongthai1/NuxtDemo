<template>
  <v-card
    elevation="0"
    style="
      background: #3a1c71;
      background: -webkit-linear-gradient(to right, #ffaf7b, #d76d77, #3a1c71);
      background: linear-gradient(to right, #ffaf7b, #d76d77, #3a1c71);
    "
  >
    <v-spacer></v-spacer>
    <v-row class="space" >
      <v-col
        class="max-w-sm rounded overflow-hidden shadow-lg mb-2"
        v-for="item in data"
        :key="item.id"
      >
        <v-img
          class="w-full"
          alt="Sunset in the mountains"
          max-height="150"
          max-width="250"
          v-bind:src="item.image"
        >
        </v-img>
        <div class="px-6 py-4 pb-2">
          <div class="font-bold text-xl mb-2 text-no-wrap">
            {{ item.title }}
          </div>
          <p class="text-gray-700 text-base text-no-wrap">
            {{ item.desciption }}
          </p>
        </div>
      </v-col>
    </v-row>
    <v-row class="space">
      <v-col
        class="max-w-sm rounded overflow-hidden shadow-lg mb-2"
        v-for="item in data"
        :key="item.id"
      >
        <v-img
          class="w-full"
          alt="Sunset in the mountains"
          max-height="150"
          max-width="250"
          v-bind:src="item.image"
        >
        </v-img>
        <div class="px-6 py-4 pb-2">
          <div class="font-bold text-xl mb-2 text-no-wrap">
            {{ item.title }}
          </div>
          <p class="text-gray-700 text-base text-no-wrap">
            {{ item.desciption }}
          </p>
        </div>
      </v-col>
    </v-row>
    <v-row class="space">
      <v-col
        class="max-w-sm rounded overflow-hidden shadow-lg mb-2"
        v-for="item in data"
        :key="item.id"
      >
        <v-img
          class="w-full"
          alt="Sunset in the mountains"
          max-height="150"
          max-width="250"
          v-bind:src="item.image"
        >
        </v-img>
        <div class="px-6 py-4 pb-2">
          <div class="font-bold text-xl mb-2 text-no-wrap">
            {{ item.title }}
          </div>
          <p class="text-gray-700 text-base text-no-wrap">
            {{ item.desciption }}
          </p>
        </div>
      </v-col>
    </v-row>
    <Pagination />
  </v-card>
</template>

<style lang="postcss" scoped>
.badge {
  @apply inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700;
  &:hover {
    @apply bg-gray-300;
  }
}
</style>
<style>
.space {
  padding-left: 40px;
  padding-top: 20px;
  padding-right: 40px;
}
* {
  box-sizing: border-box;
}
</style>
<script>
import JsonData from "../data/data.json";
export default {
  data() {
    return {
      data: JsonData,
    };
  },
};
</script>
