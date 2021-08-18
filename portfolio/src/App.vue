<template>
  <v-app>
    <v-main>
      <portfolio></portfolio>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import Portfolio from "@/components/Portfolio";
export default {
  name: 'App',

  data: () => ({
    //
  }),
  components:{
    Portfolio,
  }
};
</script>
