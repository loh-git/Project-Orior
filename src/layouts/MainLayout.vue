<template>
  <q-layout view="hHr Lpr fFr">

    <q-header class="bg-primary text-white" reveal>
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="~/assets/logo.png" style="height: 1.5em; width: 2em;"/>
          </q-avatar>
        </q-toolbar-title>
        <q-btn dense flat round icon="la la-bars" @click="right = !right" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="right"
      side="right"
      overlay
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Menu
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>
    <q-page-container>
            <router-view />
        
    </q-page-container>
    
    

    
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Home',
    caption: '',
    icon: 'la la-home',
    link: '#'
  },
  {
    title: 'About Me',
    caption: '',
    icon: 'las la-portrait',
    link: '#'
  },
  {
    title: 'Skills',
    caption: '',
    icon: 'las la-code',
    link: '#'
  },
  {
    title: 'Projects',
    caption: '',
    icon: 'las la-folder-open',
    link: '#'
  },
  {
    title: 'LinkedIn',
    caption: 'https://linkedin.com/in/loh',
    icon: 'lab la-linkedin-in',
    link: 'https://linkedin.com/in/loh'
  },
  {
    title: 'GitHub',
    caption: 'https://github.com/loh-git',
    icon: 'lab la-github',
    link: 'https://github.com/loh-git'
  }
];
export default {
  name: "MainLayout",
  components: { EssentialLink },
  data () {
    return {
      right: false,
      essentialLinks: linksData
    }
  }
}
</script>
