<template>
<v-main>
    <v-app-bar color="darkgrey">
      <v-avatar
        :color="$vuetify.breakpoint.smAndDown ? 'grey darken-1' : 'transparent'"
        size="32"
      ></v-avatar>

      <v-tabs centered class="ml-n9" color="grey darken-1">
        <v-tab v-for="link in links" :key="link">
          {{ link }}
        </v-tab>
      </v-tabs>

      <v-avatar
        class="hidden-sm-and-down"
        color="grey darken-1 shrink"
        size="32"
      ></v-avatar>
    </v-app-bar>
</v-main>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      links: ["Dashboard", "Messages", "Profile", "Updates"],
    };
  },
};
</script>

<style scoped>
.app{
    height: 50px;
}
</style>