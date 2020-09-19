<template>
  <div>
     <v-row>
      <v-col cols="12" sm="6" md="3">
        <v-text-field label="Regular" v-model="search"></v-text-field>
      </v-col>
      <v-btn class="mx-2" fab dark small color="primary" @click="searchItem">
      <v-icon dark>mdi-minus</v-icon>
    </v-btn>
    </v-row>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'Search',
  data: () => ({
    search: ""
  }),
  methods: {
    searchItem () {
      axios.get("https://pixabay.com/api/?key=18325849-94cafec8b0f30985ae8cfbdde&q="+this.search+"&image_type=photo")
        .then(res => {
          const results = res.data
          this.$emit("emitResults", results)
        })
    }
  }
}
</script>

<style>
</style>
