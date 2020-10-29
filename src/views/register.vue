<template>
  
  
  <v-container>
      <h2>กรอกข้อมูลการสมัครสมาชิก</h2>
    <v-form ref="form" v-model="valid" lazy-validation>
        
      <v-row>
        <!--  -->
        
        <v-col cols="6">
          <v-text-field
            v-model="name"
            :counter="30"
            :rules="nameRules"
            label="ชื่อ"
            required
          ></v-text-field
        ></v-col>
        
      </v-row>
      <v-row>
       <!-- นามสกุล -->
        <v-col cols="6">
          <v-text-field
            v-model="lastname"
            :counter="30"
            :rules="lastnameRules"
            label="นานสกุล"
            required
          ></v-text-field
        ></v-col>
      </v-row>

    
      <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
        สมัครสมาชิก
      </v-btn>

    </v-form>
  </v-container>
</template>

<script>
import axios from "axios";

export default {
  data: () => ({
    valid: false,

    name: "",
    nameRules: [
      v => !!v || "กรุณากรอกชื่อ",
    ],

    lastname: "",
    lastnameRules: [
      v => !!v || "กรุณากรอกนามสกุล",
    ],

    search: "",
    headers: [
      {
        text: "ชื่อ - นามสกุล",
        value: "fullname"
      }
    ],

    desserts: []
  }),

  methods: {
    validate() {
      if (this.$refs.form.validate()) {


        axios.post("http://localhost:3000/api/register", {
            "firstname": this.name,
            "lastname": this.lastname
          }).then((res) => {
            console.log(res)
          });

      }
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    }
  }
};
</script>

<style></style>
