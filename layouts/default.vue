<template>
  <v-app
    style="
      background: #3a1c71;
      background: -webkit-linear-gradient(to right, #ffaf7b, #d76d77, #3a1c71);
      background: linear-gradient(to right, #ffaf7b, #d76d77, #3a1c71);
    "
  >
    <v-navigation-drawer
      style="background: #606791"
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="text-no-wrap">{{
              item.title
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-spacer></v-spacer>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app style="background: #90caf9">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>
      <v-toolbar-title>{{ title }}</v-toolbar-title>
      <v-spacer />
      <v-menu offset-y open-on-hover>
        <template v-slot:activator="{ on }">
          <v-avatar color="white" size="38" v-on="on">
            <button class="primary--text headline">A</button>
          </v-avatar>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            @click="selectSection(item)"
          >
            <v-list-item-title>{{ item.name }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <v-spacer>
        <List />
      </v-spacer>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/",
        },
        { name: "test@gmail" },
        { name: "Profile" },
        { name: "Logout" },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Show pictures",
    };
  },

  methods: {
    selectSection(item) {
      this.selectedSection = item;
    },
  },
};
</script>
