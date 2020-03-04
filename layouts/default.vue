<template>
  <v-app dark>
    <v-app-bar :clipped-left="clipped" fixed dense app>
      <v-toolbar-title v-text="title" />
      <v-spacer></v-spacer>
      <v-btn text>
        Home
      </v-btn>
      <v-btn text>
        Sign Up
      </v-btn>
      <v-btn text>
        Login
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer app :clipped="clipped">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Categories
          </v-list-item-title>
          <v-list-item-subtitle>
            Start Shopping
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app absolute>
      <v-container fluid>
        <div class="d-flex flex-column justify-center align-center">
          <h3>Categories</h3>
          <nuxt-link to="#">Laptops</nuxt-link>
          <nuxt-link to="#">Desktops</nuxt-link>
          <nuxt-link to="#">Cameras</nuxt-link>
          <nuxt-link to="#">TVs</nuxt-link>
          <nuxt-link to="#">Speakers</nuxt-link>
          <nuxt-link to="#">Video Games</nuxt-link>
          <nuxt-link to="#">Cell Phones</nuxt-link>
        </div>
      </v-container>
      <span>&copy; {{ new Date().getFullYear() }} ViperSoft, LLC</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: false,
      miniVariant: false,
      title: 'ViperTech',
      items: [
        {
          icon: 'mdi-laptop',
          title: 'Laptops'
        },
        {
          icon: 'mdi-desktop-tower-monitor',
          title: 'Desktops'
        },
        {
          icon: 'mdi-camera',
          title: 'Cameras'
        },
        {
          icon: 'mdi-television',
          title: 'TVs'
        },
        {
          icon: 'mdi-speaker-wireless',
          title: 'Speakers'
        },
        {
          icon: 'mdi-gamepad',
          title: 'Video Games'
        },
        {
          icon: 'mdi-cellphone',
          title: 'Cell Phones'
        }
      ]
    }
  }
}
</script>
