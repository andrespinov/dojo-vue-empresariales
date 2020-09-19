<template>
  <div>
    <v-row justify="space-around">
      <v-col cols="4" v-for="image in images" v-bind:key="image.id">
        <v-card>
          <v-img v-bind:src="image.userImageURL"></v-img>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>

export default {
  name: 'ImageList',
  props: {
    images: Array
  }
}
</script>

<style>
</style>
