<template>
  <v-card>
      <v-card-title>
        <v-container>
          <v-row
            class="align-center"
            v-for="(item, index) in todos"
            :key="index"
          >
            <v-col cols="12" class="d-flex flex-row align-center pa-0">
              <v-checkbox class="mr-2"></v-checkbox>
              <span>{{ item.title }}: {{item.id}}</span>
              <v-spacer></v-spacer>
              <v-btn @click="$emit('onRemove', item.id)" color="error">x</v-btn>
            </v-col>
            <v-col cols="12">
              <v-divider></v-divider>
            </v-col>
          </v-row>
        </v-container>
      </v-card-title>
    </v-card>
</template>

<script>
export default {
props:["todos"]
}
</script>

<style>

</style>