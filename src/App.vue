<template>
  <v-app>
    <v-app-bar app 
      color='blue'
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>EC2 INSTANCE STATUS</v-toolbar-title>
    </v-app-bar>
    
    <v-main>
      <v-btn 
        white
        rounded
        block
        color='white'
        onclick='location.reload(true)'
      >
        <v-icon dark>reload</v-icon>
      </v-btn>
      
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
