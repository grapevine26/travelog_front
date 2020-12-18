<template>
  <v-app>
    <v-container>
      <v-app-bar flat :dark="dark_bar" color="none" style="background: none"
                 :class="{ change_color: scrollPosition > 50 }"
                 elevate-on-scroll scroll-target="#scrolling">
        <div class="d-flex align-center">
          <v-toolbar-title>
            <nuxt-link nuxt to="/" class="link">Leo & Heidi Blog</nuxt-link>
          </v-toolbar-title>
        </div>

        <v-spacer></v-spacer>

        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn v-for="item in menu" :key="item.icon" nuxt :to="item.link" text>
            {{ item.title }}
          </v-btn>
        </v-toolbar-items>

        <v-spacer></v-spacer>

        <v-btn to="/login" text class="hidden-sm-and-down">
          <span>Login</span>
        </v-btn>

        <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = true">
          <v-icon class="menu_icon">mdi-menu</v-icon>
        </v-app-bar-nav-icon>
      </v-app-bar>

      <v-navigation-drawer v-model="drawer" app temporary right hide-overlay>
        <v-list style="padding-top: 0">
          <v-list-item-group>
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
                <nuxt-link to="/login" class="link">Login</nuxt-link>
              </v-list-item-title>
            </v-list-item>
            <v-divider></v-divider>
            <v-list-item v-for="item in menu" :key="item.icon">
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
                <nuxt-link :to="item.link" class="link">
                  {{ item.title }}
                </nuxt-link>
              </v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>

      <v-main>
        <v-sheet id="scrolling" style="background: none">
          <transition name="fade">
            <nuxt/>
          </transition>
        </v-sheet>
      </v-main>
    </v-container>
  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        fixed: false,
        scrollPosition: null,
        drawer: false,
        menu: [
          {icon: 'mdi-account-supervisor-circle', title: 'Who Are We', link: '/whoarewe'},
          {icon: 'mdi-animation', title: 'Memories', link: '/memories'},
          {icon: 'mdi-map-marker-radius', title: 'Footprints', link: '/footprints'},
          {icon: 'mdi-lightbulb-on', title: 'Tips', link: '/tips'},
          {icon: 'mdi-email-send', title: 'Contact', link: '/contact'},
        ],
      }
    },
    computed: {
      dark_bar: function () {
        return this.scrollPosition > 50;
      }
    },
    mounted() {
      window.addEventListener('scroll', this.updateScroll)
    },
    methods: {
      updateScroll() {
        this.scrollPosition = window.scrollY;
      },
      menuItems() {
        return this.menu
      },
    },
  }
</script>

<style>
  .fade-enter-active,
  .fade-leave-active {
    transition-property: opacity;
    transition-duration: 0.25s;
  }

  .fade-enter-active {
    transition-delay: 0.25s;
  }

  .fade-enter,
  .fade-leave-active {
    opacity: 0;
  }
  .container {
    padding: 0;
  }
  .link {
    text-decoration: none;
    color: inherit !important;
  }

  .menu_icon {
    font-size: 33px !important;
  }

  .change_color {
    position: fixed !important;
    background: #454545c2 !important;
    top: 0 !important;
    z-index: 5 !important;
  }

  #scrolling {
    height: 100%;
  }

</style>
