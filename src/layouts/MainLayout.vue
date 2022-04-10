<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"></q-btn>

        <q-toolbar-title>
          MyBanking
        </q-toolbar-title>


      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <!--  Banks  -->
        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <q-item v-ripple clickable to="/">
          <q-item-section avatar>
            <q-icon color="black" name="account_balance"></q-icon>
          </q-item-section>
          <q-item-section>
            <q-item-label>Banks</q-item-label>
          </q-item-section>
        </q-item>

        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <!--  Mortgage Calculator  -->
        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <q-item v-ripple clickable to="/calc">
          <q-item-section avatar>
            <q-icon color="black" name="calculate"></q-icon>
          </q-item-section>
          <q-item-section>
            <q-item-label>Mortgage Calculator</q-item-label>
          </q-item-section>
        </q-item>


        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <!--  WebApp Version  -->
        <!--  -------------------------------------------------------------------------------------------------------------- -->
        <p class="q-pa-md"><strong>App Version - {{appVersion}}</strong></p>
<!--        <EssentialLink-->
<!--          v-for="link in essentialLinks"-->
<!--          :key="link.title"-->
<!--          v-bind="link"-->
<!--        />-->
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: {
    EssentialLink
  },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      appVersion: "2022.0", // Текущая версия ПО
    }
  }
}
</script>
