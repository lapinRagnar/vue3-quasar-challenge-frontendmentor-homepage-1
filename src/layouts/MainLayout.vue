<template>
  <q-layout view="hHh Lpr lFf">

    <q-header>

      <q-toolbar class="my-background-color " style="height: 100px;">

        <div class="row full-width my-padding-x">

          <q-toolbar-title class="text-h4 text-weight-bold">
            W.
          </q-toolbar-title>

          <div class="row">

            <q-tabs
              v-model="tab"
              shrink
              align="left"
              no-caps
              active-color="red-4"
              active-class="my-active-class"
              indicator-color="transparent"
              class="gt-xs"
            >
              <q-tab name="tab1" label="Home" />
              <q-tab name="tab2" label="New" />
              <q-tab name="tab3" label="Popular" />
              <q-tab name="tab4" label="Trending" />
              <q-tab name="tab5" label="Categories" />
            </q-tabs>

            <q-btn
              flat
              dense
              round
              icon="menu"
              aria-label="Menu"
              @click="toggleLeftDrawer"
              class="lt-sm"
            />

          </div>


        </div>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
    >
      <q-list>
        rien
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

  import { defineComponent, ref } from 'vue'


export default defineComponent({
  name: 'MainLayout',

  components: {},

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },
      tab: ref('tab1')
    }
  }
})
</script>

<style lang="scss">

  /* .my-background-color {
    background-color: rgba(254, 253, 249, 1);
  } */


  .my-padding-x{
    padding-left: 100px;
    padding-right: 100px;
  }

  .my-active-class{
    color: aqua;
  }

</style>
