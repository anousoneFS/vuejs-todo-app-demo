<template>
  <!-- Todo Add -->
  <v-row>
    <v-col cols="10">
      <v-text-field name="name" label="task" id="id" v-model="taskTextField">
      </v-text-field>
    </v-col>
    <v-col cols="2">
      <v-btn block color="success" @click="addTask">Add</v-btn>
    </v-col>
  </v-row>
</template>

<script>

// import uuid from "uuid";
import {uuid} from "vue-uuid";

export default {
  name: "todoadd",
  data(){
      return {
          taskTextField: ""
      }
  },
  methods:{
      addTask(){
          let task ={
            id : uuid.v1,
            title : this.taskTextField,
            completed: false
          }
          this.$emit("onSubmit", task);
          this.taskTextField = ""
      }
  }
};
</script>

<style></style>
