<template>
  <v-app drak>
    <v-navigation-drawer
        v-if="drawShow"
        dark
        fixed
        src="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
        permanent
    >
      <v-list-item>
        <v-list-item-avatar>
          <img src="https://avatars.githubusercontent.com/u/46031285?s=460&v=4">
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title class="title">
            Suho Kang
          </v-list-item-title>
          <v-list-item-subtitle>
            Software Developer
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider/>

      <v-list dense nav>
        <v-list-item
            v-for="item in items"
            :key="item.title"
            link
            :to="`#${item.title.toLowerCase()}`"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- page content -->
    <v-main v-bind:style="[drawShow ? {'margin-left': '256px'} : {'margin-left': '0px'}]">
      <v-app-bar dense>
        <div class="app-bar">
          <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
          <p>Suho Vincent Kang</p>
        </div>
      </v-app-bar>
      <slot/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    drawShow: true,
    items: [
      {title: 'About', icon: 'mdi-account-box'},
      {title: 'Project', icon: 'mdi-apps'},
      {title: 'Education', icon: 'mdi-school-outline'},
      {title: 'Contact', icon: 'mdi-message-text-outline'},
    ],
    right: null,
  }),
  methods: {
    toggleDrawer: function () {
      this.drawShow = !this.drawShow
    }
  }

}
</script>

<static-query>
query {
metadata {
siteName
}
}
</static-query>

<style>
html {
  scroll-behavior: smooth;
}

.v-application--wrap {
  flex-direction: row;
}

.main-container {
  flex: 1 0;
  margin-left: 256px;
}

.app-bar {
  display: flex;
  align-items: center
}

.app-bar p {
  margin-bottom: 0;
}
</style>
