<template>
  <v-card elevation="4" height="400px" width="700px">
    <v-card-title primary-title>
      <div>
        <h3 class="headline mb-0">NUMBER OF MENTIONS</h3>
      </div>
    </v-card-title>
    <v-card-text>
      <v-layout>
        <v-flex xs4 v-for="social in socials" :key="social.id" class="justify-center">
          <v-progress-circular
            :rotate="0"
            :size="120"
            :width="10"
            :value="social.value"
            :color="social.color"
            class="text-xs-center"
          >
            <v-img :src="social.image" contain height="40"></v-img>
            <br>
            <div style="line-height: 100%; color:black">
              <span style="font-weight: bold; font-size: 1.5em; display:block;">{{social.count}}</span>
              <small>{{social.unit}}</small>
            </div>
          </v-progress-circular>
        </v-flex>
      </v-layout>
      <v-layout class="mt-3">
        <v-flex xs4 v-for="social in socials" :key="social.id" class="justify-center">
          <v-img :src="social.chart" contain max-width=200></v-img>
        </v-flex>
      </v-layout>
      <v-layout class="mt-3">
        <v-flex xs4 v-for="social in socials" :key="social.id" class="justify-center">
          <span>{{social.name}}</span>
        </v-flex>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "SocialStats",
  data: () => ({
    socials: [
      {
        id: 1,
        name:'Twitter',
        image: require("../assets/twitter.png"),
        count: "31M",
        unit: "Tweets",
        color: "#00acee",
        value: 100,
        chart: require("../assets/twitter-chart.png")
      },
      {
        id: 2,
        name:'Message Boards',
        image: require("../assets/message.png"),
        count: "49K",
        unit: "Message",
        color: "#36E234",
        value: 0,
        chart: require("../assets/message-chart.png")
      },
      {
        id: 3,
        name:'Blogs',
        image: require("../assets/blog.png"),
        count: "41K",
        unit: "Message",
        color: "#F87000",
        value: 0,
        chart: require("../assets/blog-chart.png")
      }
    ]
  })
};
</script>

<style scoped>
.justify-center {
  display: flex;
  justify-content: center;
}
</style>
