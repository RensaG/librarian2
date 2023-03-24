<template>
  <v-card>
    <v-toolbar color="cyan" dark>
      <v-toolbar-side-icon></v-toolbar-side-icon>

      <v-toolbar-title>Inbox</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-toolbar>

    <v-list three-line>
      <template v-for="(item, index) in items">
        <v-subheader v-if="item.header" :key="item.header">
          {{ item.header }}
        </v-subheader>

        <v-divider
          v-else-if="item.divider"
          :key="index"
          :inset="item.inset"
        ></v-divider>

        <v-list-tile v-else :key="item.title" avatar>
          <v-list-tile-content>
            <v-list-tile-avatar>
              <img :src="item.img" />
            </v-list-tile-avatar>
            <div>{{ item.title }}</div>
            <div>{{ item.subtitle }}</div>
          </v-list-tile-content>
        </v-list-tile>
      </template>
    </v-list>
  </v-card>
</template>


<script>
import bookList from "../data/books.json";
export default {
  data() {
    return {
      items: bookList,
    };
  },
};
</script>

<style lang="scss" scoped>
</style>