<template>
<v-app>

  <v-content>
    <v-container fluid>
      <SocialStats/>
    </v-container>
  </v-content>

</v-app>
</template>

<script>
import SocialStats from './components/SocialStats'

export default {
  name: 'App',
  components: {
    SocialStats
  },
  data () {
    return {
      //
    }
  }
}
</script>
