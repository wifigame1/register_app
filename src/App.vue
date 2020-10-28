<template>
  <!-- App.vue -->

  <v-app>
    <!-- เมนูด้านข้าง -->
    <v-navigation-drawer app clipped v-model="drawer">
      <!-- ปุ่มกด -->
      <v-container>
        <v-row>
          <v-col cols="12">
            <v-btn to="/" class="mb-3" color="blue" dark block="">หน้าแรก</v-btn>
            <v-btn to="/register" class="mb-3" color="green" dark block=""
              >สมัครสมาชิก</v-btn
            >
            <v-btn to="/About" class="mb-3" color="red" block="" dark
              >เกี่ยวกับเรา</v-btn
            >
          </v-col>
        </v-row>


      </v-container>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <!-- -->
      <v-btn
        class="ma-2"
        
        
        @click="drawer = !drawer"
        
      >
        <v-icon color="dark">mdi-format-list-bulleted-square</v-icon>
      </v-btn>

      <v-toolbar-title>
        ระบบเก็บข้อมูลร้านค้า
      </v-toolbar-title>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- <p>main</p> -->
      <!-- If using vue-router -->
      <router-view></router-view>
    </v-main>

    <v-footer app>
      <!-- -->
      <span>&copy; RMUTL {{ new Date().getFullYear() + 543 }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      right: null,
      message: "RMUTL",
      drawer: null,
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kodchasan&display=swap");

#app {
  font-family: "Kodchasan", sans-serif;
}
</style>
