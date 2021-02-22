<template>
  <v-app>
    <v-app-bar app 
      color='blue'
      dark
      scroll-target="#scrolling-techniques-6"
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>EC2 INSTANCE STATUS</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>
    <v-main>
      <ec2_instance/>
    </v-main>
  </v-app>
</template>

<script>
import ec2_instance from './components/ec2_instance';

export default {
  name: 'App',

  components: {
    ec2_instance
  },

  data: () => ({
    //
  }),
};
</script>
