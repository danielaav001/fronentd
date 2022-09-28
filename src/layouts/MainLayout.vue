<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="las la-bars"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>menu</q-toolbar-title>

        <div>
          <i class="las la-moon"></i>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header>luna bonny</q-item-label>

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
import { defineComponent, ref } from 'vue';
import EssentialLink from 'components/EssentialLink.vue';

const linksList = [
  {
    title: 'materiales',
    caption: '',
    icon: 'las la-palette',
    link: 'https://quasar.dev',
    
  },
  {
    title: 'proveedor',
    caption: '',
    icon: 'las la-user-secret',
    link: 'https://github.com/quasarframework',
  },
  {
    title: 'inventario',
    caption: '',
    icon: 'las la-paste',
    link: 'https://chat.quasar.dev',
  },
  {
    title: 'usuario',
    caption: '',
    icon: 'las la-user-tie',
    link: 'https://forum.quasar.dev',
  },
  {
    title: 'reguistrar compras',
    caption: '',
    icon: 'las la-cash-register',
    link: 'https://twitter.quasar.dev',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
