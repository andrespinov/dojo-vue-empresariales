<template>
  <v-app>
    <div id="app">
      <Toolbar />
      <Search v-on:emitResults="emitResults" />
      <ImageList v-bind:images="items" />
    </div>
  </v-app>
</template>

<script>
import Toolbar from './components/Toolbar';
import Search from './components/Search';
import ImageList from './components/ImageList';

export default {
  name: 'App',

  components: {
    Toolbar,
    Search,
    ImageList
  },
  data: () => ({
    items: []
  }),
  methods: {
    emitResults(response) {
      this.items = response.hits
      console.log(this.items)
    }
  }
};
</script>
