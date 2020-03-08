<template lang="pug">
v-app.application
  v-navigation-drawer(persistent :mini-variant.sync='miniVariant', :clipped='clipped', v-model='drawer', enable-resize-watcher   fixed app style='overflow: hidden;')
    v-list(style="padding: 0;")
      v-list-tile(avatar style="background-color: darkgrey")
        v-list-tile-avatar
          i.material-icons.white--text beach_access
        v-list-tile-title.title.white--text
           | Topical Tropics

    v-divider
    v-list
      v-list-tile.dignity(router v-for='item in items', :key='item.title', @click="drawer = false", style='height: 40px', :to='item.to', active-class="blue-grey lighten-3 white--text" exact)
        v-list-tile-action
          v-icon(v-html='item.icon')

        v-list-tile-content
          v-list-tile-title(v-text='item.title', style="color: inherit")
  
  v-toolbar(app :clipped-left='clipped')
    v-toolbar-side-icon(@click.stop='drawer = !drawer')

    v-btn.mr-4(icon @click.stop='miniVariant = !miniVariant')
      v-icon(v-html="miniVariant ? 'chevron_right' : 'chevron_left'")

    v-btn(icon)
      i.fas.fa-sun.fa-3x.mr-2

    v-toolbar-title.dignity.ml-0(v-text='title')

    v-spacer

    v-btn(icon='' to='/new-york')
      v-icon highlight_off

  v-content
    router-view

  v-footer.hidden-sm-and-down(:fixed='fixed' app)
    span.ml-3
      v-icon beach_access
      | &nbsp; Clonado na Samboja pelo Gran Bret&ocirc;nio 2018 e honi soit qui mal y pense
</template>


<style lang="scss">

@import url("https://fonts.googleapis.com/css?family=News+Cycle|Material+Icons");

.application, .title {
  font-family: "News Cycle", sans-serif;
  font-weight: 300;
  font-style: normal
}

  body, html, .application {
    font-family: 'News Cycle', sans-serif !important;
  }

  h1, h2, h3, h4, h5, h6, .headline, .title, .subheading  {
    font-family: 'News Cycle', sans-serif !important;
    font-weight: 300;
  }

  .dignity {
    font-family: 'News Cycle', sans-serif !important;
    font-weight: 300;
  }

  .display-1, .display-2, .display-3, .display-4, .headline, .title, .subtitle-1, .subtitle-2, .body-1, .body-2, .caption   {
    font-family: 'News Cycle', sans-serif !important;
    font-weight: 300;
  }

</style>
  

<script>
export default {
  data () {
    return {
      clipped: true,
      drawer: false,
      fixed: true,
      items: [
        { icon: 'accessibility', title: 'Bom Dia, Meia-Note', to: '/' },
        { icon: 'directions_bike', title: 'Tour de Ibirapuera', to: '/bicicleta' },
        { icon: 'power_settings_new', title: 'Turn Me On, Dead Man', to:  '/turn-me' },
        { icon: 'business', title: 'Gotham Gothic', to: '/new-york' },
        { icon: 'edit', title: 'Rubem Fonseca', to: '/grande-arte' },
        { icon: 'commute', title: 'Action Painting', to: '/pollock' },
        { icon: 'restaurant', title: 'Hungry Generation', to: '/hungerers' },
        { icon: 'invert_colors', title: 'Farewell, Angelina', to: '/angelina' },
        { icon: 'ring_volume', title: 'Hello World My Ass', to: '/my-ass' }
    ],
      miniVariant: false,
      right: false,
      rightDrawer: false,
      title: 'Engenho Novo LLC'
    }
  },
  name: 'App'
}
</script>
